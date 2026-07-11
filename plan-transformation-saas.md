# Plan d’implémentation — ERP Node.js local mono-utilisateur vers SaaS multi-utilisateur

## Contexte

Ce document décrit un plan d’implémentation pour transformer un ERP Node.js local mono-utilisateur en SaaS multi-utilisateur.

Contexte technique et produit connu :

- frontend HTML/JavaScript ;
- backend Node HTTP natif ;
- état global JSON local ;
- aucune authentification ;
- aucune base SQL ;
- aucune isolation des données ;
- futur modèle utilisateur → organisation → boutique ;
- cible PostgreSQL ;
- paiement plus tard, pas maintenant.

Contraintes :

- ne pas supposer de détail métier absent ;
- viser une bêta privée ;
- signaler les décisions à valider lundi ;
- exclure le paiement de cette phase.

## 1. Schéma PostgreSQL minimal pour une bêta privée

### Principes

Le schéma minimal doit distinguer :

- l’identité : utilisateur ;
- le tenant SaaS : organisation ;
- l’unité opérationnelle : boutique ;
- les droits d’accès : appartenance utilisateur ↔ organisation ;
- les données métier migrées depuis le JSON ;
- les sessions applicatives ;
- la traçabilité des migrations.

Comme les objets métier actuels ne sont pas décrits, le schéma de bêta ne doit pas inventer de tables métier comme `products`, `orders` ou `customers`. Une table générique `app_entities` en `jsonb` permet d’absorber l’existant sans présumer de sa structure.

### Table `users`

Représente les comptes humains pouvant se connecter.

Champs minimaux :

- `id` ;
- `email` ;
- `password_hash` ;
- `display_name` ;
- `created_at` ;
- `updated_at` ;
- `disabled_at`.

Contraintes :

- `email` unique ;
- `email` obligatoire ;
- `password_hash` obligatoire dès que l’authentification par mot de passe est activée ;
- `disabled_at` nullable pour désactiver un compte sans suppression.

### Table `organizations`

Représente le tenant principal.

Champs minimaux :

- `id` ;
- `name` ;
- `created_at` ;
- `updated_at` ;
- `disabled_at`.

Contraintes :

- `name` obligatoire ;
- unicité globale du nom à valider selon le produit.

### Table `organization_memberships`

Relie les utilisateurs aux organisations.

Champs minimaux :

- `id` ;
- `user_id` ;
- `organization_id` ;
- `role` ;
- `created_at` ;
- `updated_at` ;
- `disabled_at`.

Contraintes :

- `user_id` référence `users(id)` ;
- `organization_id` référence `organizations(id)` ;
- couple `(user_id, organization_id)` unique ;
- `role` obligatoire.

Rôles minimaux possibles pour la bêta :

- `owner` ;
- `admin` ;
- `member`.

Décision à valider lundi : confirmer les rôles nécessaires pour la bêta. Si l’objectif est strictement privé et contrôlé, `owner` et `member` peuvent suffire au départ.

### Table `shops`

Représente les boutiques appartenant à une organisation.

Champs minimaux :

- `id` ;
- `organization_id` ;
- `name` ;
- `created_at` ;
- `updated_at` ;
- `disabled_at`.

Contraintes :

- `organization_id` référence `organizations(id)` ;
- `name` obligatoire ;
- unicité éventuelle de `(organization_id, name)` à valider.

Décision à valider lundi : une organisation peut-elle avoir plusieurs boutiques dès la bêta, ou doit-on créer une seule boutique par organisation pour simplifier la migration initiale ?

### Table `app_entities`

Table de transition pour stocker les données métier issues du JSON local sans présumer de leur structure exacte.

Champs minimaux :

- `id` ;
- `organization_id` ;
- `shop_id` ;
- `entity_type` ;
- `legacy_id` ;
- `data` ;
- `created_at` ;
- `updated_at` ;
- `deleted_at`.

Contraintes :

- `organization_id` référence `organizations(id)` ;
- `shop_id` référence `shops(id)` ;
- `entity_type` obligatoire ;
- `data` en `jsonb` ;
- unicité recommandée sur `(shop_id, entity_type, legacy_id)` lorsque `legacy_id` existe.

Rôle de cette table :

- absorber rapidement l’existant JSON ;
- éviter de deviner les tables métier absentes du contexte ;
- permettre une migration SaaS progressive ;
- préparer ultérieurement une normalisation métier table par table.

Décision à valider lundi : accepter temporairement une table `jsonb` générique en bêta, ou exiger immédiatement des tables relationnelles métier spécifiques après inventaire du JSON.

### Table `auth_sessions`

Représente les sessions applicatives.

Champs minimaux :

- `id` ;
- `user_id` ;
- `session_token_hash` ;
- `created_at` ;
- `expires_at` ;
- `revoked_at` ;
- `last_seen_at`.

Contraintes :

- `user_id` référence `users(id)` ;
- `session_token_hash` unique ;
- expiration obligatoire.

Décision à valider lundi : choisir le mécanisme d’authentification exact, par exemple cookie HTTP-only avec session serveur ou JWT signé. Pour une bêta privée avec backend Node HTTP natif, une session serveur persistée en base est généralement plus simple à révoquer.

### Table `migration_runs`

Trace les imports depuis JSON vers PostgreSQL.

Champs minimaux :

- `id` ;
- `source_file` ;
- `target_organization_id` ;
- `target_shop_id` ;
- `status` ;
- `started_at` ;
- `finished_at` ;
- `summary` ;
- `error_message`.

Rôle :

- savoir quel fichier JSON a été migré ;
- garder un historique d’import ;
- faciliter rollback et diagnostic.

### Table `audit_events` optionnelle mais recommandée

Pour une bêta privée, elle peut être minimaliste.

Champs minimaux :

- `id` ;
- `organization_id` ;
- `shop_id` ;
- `user_id` ;
- `action` ;
- `entity_type` ;
- `entity_id` ;
- `created_at` ;
- `metadata`.

Rôle :

- diagnostiquer les accès ;
- tracer les opérations sensibles ;
- vérifier l’isolation en cas d’incident.

Décision à valider lundi : inclure `audit_events` dès la bêta ou reporter après stabilisation de l’authentification et de la migration.

## 2. Liste des tables et relations

### Tables minimales obligatoires

| Table | Rôle | Obligatoire bêta |
| --- | --- | --- |
| `users` | Comptes utilisateurs | Oui |
| `organizations` | Tenants SaaS | Oui |
| `organization_memberships` | Accès utilisateur ↔ organisation | Oui |
| `shops` | Boutiques appartenant aux organisations | Oui |
| `app_entities` | Données métier migrées depuis JSON | Oui, sauf si tables métier détaillées disponibles |
| `auth_sessions` | Sessions utilisateurs | Oui si auth par session |
| `migration_runs` | Traçabilité des migrations | Oui |

### Tables optionnelles recommandées

| Table | Rôle | Recommandation |
| --- | --- | --- |
| `audit_events` | Journal des actions sensibles | Recommandée pour bêta privée |
| `invitations` | Invitation d’utilisateurs | À reporter sauf besoin immédiat |
| `password_reset_tokens` | Réinitialisation mot de passe | À reporter si comptes créés manuellement |
| `api_keys` | Accès machine/API | À exclure de la bêta sauf besoin explicite |
| `billing_*` | Paiement, plans, facturation | À exclure explicitement |

### Relations

Utilisateur vers organisation :

```text
users
  1 ─── n organization_memberships n ─── 1 organizations
```

Organisation vers boutique :

```text
organizations
  1 ─── n shops
```

Boutique vers données métier :

```text
shops
  1 ─── n app_entities
```

Chaque donnée métier doit aussi porter `organization_id` pour simplifier les filtres d’isolation et éviter de devoir joindre systématiquement `shops`.

```text
organizations
  1 ─── n app_entities
```

Utilisateur vers session :

```text
users
  1 ─── n auth_sessions
```

Migration vers organisation et boutique :

```text
migration_runs
  n ─── 1 organizations
  n ─── 1 shops
```

## 3. Stratégie de migration JSON vers PostgreSQL

### Objectif

Migrer l’état global JSON local vers une structure PostgreSQL multi-tenant sans casser le fonctionnement existant et sans supposer la structure métier exacte des données.

### Principe général

La migration doit se faire en plusieurs phases :

1. inventaire du JSON existant ;
2. création d’une organisation cible ;
3. création d’une boutique cible ;
4. création d’un utilisateur propriétaire ;
5. import des objets JSON dans `app_entities` ;
6. validation comparative JSON ↔ PostgreSQL ;
7. bascule lecture seule vers PostgreSQL ;
8. bascule écriture vers PostgreSQL ;
9. archivage du JSON source.

### Ne pas supprimer immédiatement le JSON

Le fichier JSON actuel doit être conservé en lecture seule pendant la bêta.

Il servira à :

- comparer les volumes ;
- vérifier les données migrées ;
- restaurer rapidement en cas de défaut critique ;
- diagnostiquer les divergences.

### Import initial

Pour le premier import :

- créer une organisation par environnement ou client bêta ;
- créer une boutique associée ;
- créer un utilisateur `owner` ;
- importer chaque collection ou section du JSON comme `entity_type` ;
- conserver l’identifiant historique si disponible dans `legacy_id` ;
- stocker l’objet original complet dans `data`.

Exemple conceptuel :

```text
JSON source:
{
  "products": [...],
  "orders": [...],
  "settings": {...}
}

PostgreSQL:
app_entities(entity_type = "products", data = chaque produit)
app_entities(entity_type = "orders", data = chaque commande)
app_entities(entity_type = "settings", data = objet settings)
```

Si certaines sections JSON sont des objets uniques plutôt que des listes, elles peuvent être stockées avec :

```text
entity_type = nom_de_section
legacy_id = null ou clé stable
data = objet complet
```

### Mapping minimal

| Source JSON | Destination PostgreSQL |
| --- | --- |
| Fichier global | `migration_runs.source_file` |
| Section racine JSON | `app_entities.entity_type` |
| Identifiant local existant | `app_entities.legacy_id` |
| Objet complet | `app_entities.data` |
| Client/tenant bêta | `organizations` |
| Boutique cible | `shops` |
| Utilisateur propriétaire | `users` + `organization_memberships` |

### Validation post-migration

La validation doit vérifier :

- nombre total d’objets par section JSON ;
- nombre total d’objets par `entity_type` ;
- absence d’objets sans `organization_id` ;
- absence d’objets sans `shop_id` ;
- unicité des identifiants historiques quand ils existent ;
- capacité à relire les données par utilisateur connecté ;
- impossibilité de relire les données d’une autre organisation.

### Migration progressive vers tables métier

Après la bêta privée, chaque `entity_type` pourra être converti vers une table relationnelle propre.

Exemples conceptuels :

- `app_entities` avec `entity_type = "products"` → future table `products` ;
- `app_entities` avec `entity_type = "orders"` → future table `orders` ;
- `app_entities` avec `entity_type = "customers"` → future table `customers`.

Mais cette étape ne doit pas être faite tant que la structure réelle du JSON n’est pas inventoriée.

## 4. Ordre exact des étapes

### Phase 0 — Cadrage et décisions préalables

#### Étape 0.1 — Geler le périmètre bêta

Inclure :

- authentification ;
- organisations ;
- boutiques ;
- isolation des données ;
- migration JSON ;
- PostgreSQL ;
- sessions ;
- tests multi-utilisateurs.

Exclure :

- paiement ;
- plans tarifaires ;
- facturation ;
- multi-région ;
- permissions fines complexes ;
- refonte complète frontend ;
- normalisation complète de toutes les tables métier.

#### Étape 0.2 — Inventorier le JSON existant

Produire un document décrivant :

- sections racine du JSON ;
- type de chaque section : objet, tableau, scalaire ;
- champs identifiants éventuels ;
- dépendances entre objets si observables ;
- volumes approximatifs ;
- champs sensibles éventuels.

Décision à valider lundi : définir si les données sensibles doivent être masquées, chiffrées ou exclues de certains environnements.

#### Étape 0.3 — Valider le modèle tenant

À valider :

- un utilisateur peut-il appartenir à plusieurs organisations ?
- une organisation peut-elle avoir plusieurs boutiques dès la bêta ?
- faut-il sélectionner une boutique active dans l’interface ?
- faut-il un rôle par organisation uniquement, ou aussi par boutique ?

Recommandation bêta :

```text
user → organization_membership → organization → shops
```

Pas de rôle spécifique par boutique au départ, sauf besoin explicite.

### Phase 1 — Préparation PostgreSQL

#### Étape 1.1 — Ajouter PostgreSQL à l’environnement

Préparer :

- base locale de développement ;
- base de test ;
- base de staging ou bêta ;
- variables d’environnement ;
- script de création de schéma ;
- stratégie de migration SQL.

#### Étape 1.2 — Créer le schéma minimal

Créer les tables :

1. `users` ;
2. `organizations` ;
3. `organization_memberships` ;
4. `shops` ;
5. `auth_sessions` ;
6. `app_entities` ;
7. `migration_runs` ;
8. `audit_events` si validé.

#### Étape 1.3 — Ajouter les contraintes d’isolation

Toutes les tables métier ou quasi métier doivent inclure :

- `organization_id` ;
- `shop_id` si la donnée appartient à une boutique ;
- index sur `organization_id` ;
- index sur `shop_id` ;
- index composite selon les accès fréquents.

Pour `app_entities`, prévoir au minimum :

```text
organization_id
shop_id
entity_type
legacy_id
```

### Phase 2 — Authentification minimale

#### Étape 2.1 — Créer l’authentification

Mettre en place :

- création manuelle ou contrôlée d’utilisateurs ;
- connexion ;
- déconnexion ;
- sessions ;
- expiration ;
- révocation ;
- hash de mot de passe.

#### Étape 2.2 — Protéger toutes les routes backend

Avant cette étape, le backend fonctionne sans identité.

Après cette étape :

- aucune route métier ne doit répondre sans utilisateur authentifié ;
- chaque requête doit produire un contexte serveur :

```text
current_user
current_organization
current_shop
```

#### Étape 2.3 — Ajouter une sélection d’organisation et boutique

Si un utilisateur peut avoir plusieurs organisations ou boutiques, le backend doit recevoir ou déterminer :

- l’organisation active ;
- la boutique active.

Ne jamais faire confiance uniquement à un identifiant envoyé par le frontend.

Le backend doit vérifier :

```text
l’utilisateur appartient à cette organisation
la boutique appartient à cette organisation
```

### Phase 3 — Couche d’accès aux données

#### Étape 3.1 — Extraire l’accès à l’état global JSON

Identifier tous les endroits où le backend lit ou écrit l’état global JSON.

Créer une abstraction conceptuelle :

```text
readEntity
writeEntity
listEntities
deleteEntity
```

ou équivalent, sans imposer ici les noms exacts.

Le but est de ne plus accéder directement au JSON depuis les handlers HTTP.

#### Étape 3.2 — Ajouter un backend PostgreSQL derrière cette abstraction

Les lectures et écritures doivent être filtrées par :

```text
organization_id
shop_id
```

Règle absolue : aucune requête SQL métier ne doit être exécutée sans filtre tenant.

#### Étape 3.3 — Conserver temporairement le backend JSON

Pendant la transition, conserver :

- backend JSON en lecture seule ;
- backend PostgreSQL actif pour la bêta ;
- mécanisme de comparaison possible.

### Phase 4 — Migration des données

#### Étape 4.1 — Écrire un import dry-run

Le dry-run doit :

- lire le JSON ;
- détecter les sections ;
- compter les objets ;
- simuler le mapping vers `app_entities` ;
- produire un rapport ;
- ne rien écrire en base.

#### Étape 4.2 — Écrire l’import réel

L’import réel doit :

- créer une entrée `migration_runs` ;
- insérer les données dans `app_entities` ;
- rattacher chaque ligne à `organization_id` et `shop_id` ;
- enregistrer un résumé ;
- échouer proprement sans import partiel non traçable.

#### Étape 4.3 — Valider les données importées

Comparer :

- nombre d’objets source ;
- nombre d’objets cible ;
- types d’entités ;
- identifiants historiques ;
- objets invalides ;
- objets dupliqués.

#### Étape 4.4 — Activer la lecture PostgreSQL

Le backend lit depuis PostgreSQL.

Le JSON reste disponible comme sauvegarde.

#### Étape 4.5 — Activer l’écriture PostgreSQL

Le backend écrit uniquement dans PostgreSQL.

Le JSON ne doit plus être modifié.

### Phase 5 — Isolation multi-utilisateur

#### Étape 5.1 — Créer deux organisations de test

Exemple conceptuel :

```text
Organisation A
  Boutique A1
  Utilisateur A

Organisation B
  Boutique B1
  Utilisateur B
```

#### Étape 5.2 — Injecter des données distinctes

Créer des objets métier pour chaque boutique.

Vérifier que :

- l’utilisateur A voit uniquement les données A ;
- l’utilisateur B voit uniquement les données B ;
- les accès croisés échouent.

#### Étape 5.3 — Tester toutes les routes

Chaque route métier doit être testée avec :

- utilisateur non connecté ;
- utilisateur connecté à la bonne organisation ;
- utilisateur connecté à une autre organisation ;
- boutique inexistante ;
- boutique d’une autre organisation ;
- identifiant d’objet valide mais appartenant à un autre tenant.

### Phase 6 — Durcissement bêta

#### Étape 6.1 — Journalisation minimale

Logguer :

- connexions ;
- échecs de connexion ;
- changements d’organisation/boutique active ;
- créations/modifications/suppressions métier ;
- refus d’accès tenant.

#### Étape 6.2 — Sauvegardes

Prévoir :

- backup PostgreSQL régulier ;
- conservation du JSON source ;
- procédure de restauration documentée ;
- test de restauration avant bêta privée.

#### Étape 6.3 — Préparer l’exploitation bêta

Prévoir :

- création manuelle d’organisations ;
- création manuelle d’utilisateurs ;
- rattachement des utilisateurs aux organisations ;
- import JSON par organisation/boutique ;
- checklist de validation avant ouverture.

## 5. Risques et rollbacks

### Risque 1 — Fuite de données entre organisations

Causes possibles :

- requête SQL sans `organization_id` ;
- endpoint acceptant un `shop_id` non vérifié ;
- frontend filtrant les données au lieu du backend ;
- ancienne logique globale JSON encore utilisée.

Impact : critique, bloque la bêta.

Rollback :

- désactiver accès SaaS ;
- repasser temporairement en mono-tenant local ;
- auditer les logs ;
- corriger toutes les routes sans filtre tenant.

### Risque 2 — Migration incomplète ou incorrecte

Causes possibles :

- structure JSON mal comprise ;
- objets imbriqués non migrés ;
- identifiants absents ;
- types mélangés ;
- valeurs inattendues.

Impact : élevé.

Rollback :

- conserver JSON source ;
- supprimer les lignes associées à `migration_runs.id` ou à la cible `organization_id/shop_id` ;
- corriger le mapping ;
- relancer l’import.

### Risque 3 — Perte de données lors de l’écriture PostgreSQL

Causes possibles :

- écriture partielle ;
- transaction manquante ;
- crash pendant mutation ;
- conversion JSONB incorrecte.

Impact : élevé.

Rollback :

- restaurer backup PostgreSQL ;
- réimporter depuis JSON si les écritures bêta peuvent être perdues ;
- sinon rejouer les événements applicatifs si audit suffisant.

Décision à valider lundi : accepter ou non que les écritures bêta soient jetables pendant une première période de test.

### Risque 4 — Authentification insuffisante

Causes possibles :

- session non expirée ;
- token stocké en clair ;
- cookie non sécurisé ;
- absence de révocation ;
- mot de passe mal hashé.

Impact : critique.

Rollback :

- désactiver les comptes ;
- révoquer toutes les sessions ;
- forcer réinitialisation des mots de passe ;
- corriger la stratégie de session.

### Risque 5 — Couplage fort au JSON historique

Causes possibles :

- application continuant à manipuler des structures globales ;
- absence de couche d’accès aux données ;
- mélange lecture JSON / écriture SQL.

Impact : moyen à élevé.

Rollback :

- maintenir mode lecture JSON ;
- retarder l’écriture PostgreSQL ;
- refactoriser progressivement les accès.

### Risque 6 — Mauvais modèle organisation/boutique

Causes possibles :

- organisation et boutique confondues ;
- besoin réel de droits par boutique ;
- besoin multi-boutiques ignoré ;
- utilisateur devant appartenir à plusieurs organisations.

Impact : moyen.

Rollback :

- conserver modèle relationnel flexible ;
- éviter de coder des hypothèses irréversibles ;
- garder `organization_id` et `shop_id` séparés partout.

### Rollback par phase

| Phase | Rollback |
| --- | --- |
| Schéma PostgreSQL | Supprimer base ou revenir à migration précédente |
| Authentification | Désactiver middleware auth et revenir environnement local contrôlé |
| Migration dry-run | Aucun rollback nécessaire |
| Import réel | Supprimer données importées pour `migration_run` |
| Lecture PostgreSQL | Rebasculer lecture vers JSON |
| Écriture PostgreSQL | Stopper bêta, restaurer backup, réimporter |
| Multi-tenant public | Désactiver organisations supplémentaires |

## 6. Tests d’isolation multi-utilisateur

### Matrice minimale de test

Créer au minimum :

```text
User A
Organization A
Shop A1
Data A1

User B
Organization B
Shop B1
Data B1
```

Puis tester chaque route.

### Tests d’authentification

#### Test 1 — Route métier sans session

Attendu :

```text
HTTP 401
aucune donnée retournée
```

#### Test 2 — Session invalide

Attendu :

```text
HTTP 401
session rejetée
```

#### Test 3 — Session expirée

Attendu :

```text
HTTP 401
session expirée
```

### Tests d’accès organisation

#### Test 4 — User A liste ses données

Contexte :

```text
user = A
organization = A
shop = A1
```

Attendu :

```text
uniquement données A1
aucune donnée B1
```

#### Test 5 — User A tente d’accéder à Organization B

Contexte :

```text
user = A
organization demandée = B
```

Attendu :

```text
HTTP 403
aucune donnée retournée
événement de refus éventuellement journalisé
```

#### Test 6 — User A tente d’utiliser Shop B1

Contexte :

```text
user = A
shop demandée = B1
```

Attendu :

```text
HTTP 403 ou 404
aucune donnée retournée
```

Décision à valider lundi : choisir la convention `403` ou `404` pour les ressources appartenant à un autre tenant.

### Tests d’accès aux objets métier

#### Test 7 — Lecture croisée par identifiant

Contexte :

```text
User A demande un objet appartenant à User B / Organization B
```

Attendu :

```text
HTTP 404 ou 403
objet non retourné
```

#### Test 8 — Modification croisée

Contexte :

```text
User A tente de modifier un objet de Organization B
```

Attendu :

```text
HTTP 404 ou 403
aucune modification en base
```

Validation SQL conceptuelle :

```text
l’objet B conserve ses valeurs initiales
updated_at inchangé
```

#### Test 9 — Suppression croisée

Contexte :

```text
User A tente de supprimer un objet de Organization B
```

Attendu :

```text
HTTP 404 ou 403
objet B toujours présent
deleted_at inchangé si soft delete
```

### Tests de création

#### Test 10 — Création par User A

Contexte :

```text
User A crée un objet dans Shop A1
```

Attendu :

```text
organization_id = Organization A
shop_id = Shop A1
```

Le backend doit assigner ces valeurs depuis le contexte serveur, pas depuis une confiance aveugle dans le frontend.

#### Test 11 — Création avec organization_id frauduleux

Contexte :

```text
User A envoie organization_id = Organization B
```

Attendu :

```text
requête rejetée ou organization_id ignoré
aucune donnée créée dans Organization B
```

#### Test 12 — Création avec shop_id frauduleux

Contexte :

```text
User A envoie shop_id = Shop B1
```

Attendu :

```text
HTTP 403 ou 404
aucune donnée créée
```

### Tests de migration

#### Test 13 — Import dans Organization A uniquement

Attendu :

```text
toutes les lignes importées ont organization_id = A
toutes les lignes importées ont shop_id = A1
aucune ligne créée pour B
```

#### Test 14 — Import répété

Attendu selon stratégie validée :

Option A — idempotence :

```text
pas de doublons
données mises à jour ou ignorées
```

Option B — import bloqué :

```text
erreur explicite indiquant migration déjà effectuée
```

Décision à valider lundi : choisir entre import idempotent et import unique bloqué.

#### Test 15 — Import échoué

Attendu :

```text
migration_runs.status = failed
aucune donnée partielle non traçable
rapport d’erreur présent
```

### Tests de requêtes SQL

Tout accès métier doit être testé contre les erreurs suivantes :

- absence de filtre `organization_id` ;
- filtre `shop_id` seul sans vérification de l’organisation ;
- endpoint utilisant un identifiant global non scopé ;
- pagination mélangeant plusieurs organisations ;
- recherche globale non filtrée ;
- export global non filtré.

## 7. Décisions à valider lundi

### Modèle produit / tenant

À valider :

1. une organisation peut-elle contenir plusieurs boutiques dès la bêta ?
2. un utilisateur peut-il appartenir à plusieurs organisations ?
3. les rôles sont-ils uniquement au niveau organisation ?
4. faut-il des rôles par boutique ?
5. faut-il masquer l’existence des ressources interdites avec `404` au lieu de `403` ?

### Authentification

À valider :

1. authentification par email + mot de passe ?
2. création manuelle des comptes ou invitation par email ?
3. session serveur ou JWT ?
4. durée de session ?
5. politique de révocation ?
6. réinitialisation de mot de passe dès la bêta ou gestion manuelle ?

### Migration

À valider :

1. table générique `app_entities` acceptable pour bêta ?
2. faut-il normaliser immédiatement certaines entités métier ?
3. import idempotent ou import unique ?
4. les écritures de bêta doivent-elles être conservées définitivement ?
5. faut-il migrer tous les champs ou exclure certains champs sensibles ?
6. quelle organisation/boutique cible pour le JSON existant ?

### Exploitation

À valider :

1. environnement de bêta : local, VPS, cloud managé ?
2. PostgreSQL managé ou auto-hébergé ?
3. fréquence des sauvegardes ?
4. procédure de restauration attendue ?
5. niveau de logging acceptable ?
6. qui peut créer des organisations et utilisateurs ?

### Sécurité

À valider :

1. politique de mots de passe ;
2. expiration des sessions ;
3. usage obligatoire de HTTPS ;
4. stockage des secrets ;
5. chiffrement éventuel de champs sensibles ;
6. politique d’accès aux logs.

## 8. Suite de prompts courts pour Codex local

Chaque prompt correspond à une étape séparée. Ils sont volontairement courts, cadrés, et ne demandent pas à Codex de supposer des détails absents.

### Prompt 1 — Inventaire du projet

```text
Analyse le projet existant sans modifier le code. Identifie les fichiers backend Node HTTP natif, les routes HTTP, les points de lecture/écriture de l’état JSON local, et le fichier ou module qui contient l’état global. Produis une synthèse avec chemins de fichiers et responsabilités. Ne code rien.
```

### Prompt 2 — Inventaire du JSON

```text
Analyse la structure du JSON local sans modifier le code. Liste les sections racine, leur type, les champs identifiants apparents, les volumes approximatifs, et les dépendances visibles entre sections. Ne suppose aucun modèle métier absent. Ne code rien.
```

### Prompt 3 — Proposition de schéma SQL

```text
Prépare une proposition de schéma PostgreSQL minimal pour une bêta privée multi-utilisateur avec users, organizations, organization_memberships, shops, auth_sessions, app_entities et migration_runs. Ne code rien dans l’application. Si tu ajoutes un fichier SQL, limite-toi au schéma et documente les décisions à valider.
```

### Prompt 4 — Préparation migrations SQL

```text
Ajoute une structure de migrations PostgreSQL adaptée au projet actuel. Crée uniquement les fichiers nécessaires pour initialiser le schéma minimal validé. Ne modifie pas encore les routes applicatives. Ajoute une commande de vérification si le projet a déjà un système de scripts.
```

### Prompt 5 — Configuration PostgreSQL

```text
Ajoute la configuration PostgreSQL minimale via variables d’environnement. Ne mets aucun secret en dur. Prévois dev/test/bêta si la structure du projet le permet. Ne change pas encore la logique métier.
```

### Prompt 6 — Couche database

```text
Ajoute un module d’accès PostgreSQL minimal pour ouvrir/fermer une connexion et exécuter des requêtes paramétrées. Ne migre aucune route métier. Ne mets pas de try/catch autour des imports.
```

### Prompt 7 — Authentification : analyse préalable

```text
Analyse les routes actuelles et propose où insérer un middleware ou équivalent d’authentification dans le backend Node HTTP natif. Ne code rien. Liste les routes qui devront devenir protégées.
```

### Prompt 8 — Authentification minimale

```text
Implémente une authentification minimale par session serveur persistée en PostgreSQL, en respectant le style actuel du backend Node HTTP natif. Protège les routes métier identifiées. Ne modifie pas encore la migration JSON.
```

### Prompt 9 — Contexte tenant

```text
Ajoute la résolution serveur du contexte current_user, current_organization et current_shop. Vérifie que l’utilisateur appartient à l’organisation demandée et que la boutique appartient à cette organisation. Ne fais confiance à aucun organization_id ou shop_id envoyé par le frontend sans validation.
```

### Prompt 10 — Abstraction de l’état applicatif

```text
Identifie les accès directs à l’état JSON et introduis une abstraction d’accès aux données sans changer le comportement fonctionnel. L’objectif est de préparer le remplacement JSON par PostgreSQL. Garde les changements petits et testables.
```

### Prompt 11 — Lecture depuis PostgreSQL

```text
Ajoute une implémentation PostgreSQL de l’abstraction d’accès aux données en utilisant app_entities. Toutes les lectures doivent être filtrées par organization_id et shop_id issus du contexte serveur. Ne supprime pas encore le backend JSON.
```

### Prompt 12 — Écriture vers PostgreSQL

```text
Ajoute les écritures PostgreSQL dans app_entities via l’abstraction d’accès aux données. Toutes les créations/modifications/suppressions doivent être scopées par organization_id et shop_id issus du contexte serveur. Le frontend ne doit pas pouvoir forcer un autre tenant.
```

### Prompt 13 — Dry-run migration JSON

```text
Ajoute une commande de dry-run de migration JSON vers PostgreSQL. Elle doit lire le JSON local, compter les sections et objets, produire un rapport, mais ne rien écrire en base. Ne suppose pas de structure métier absente.
```

### Prompt 14 — Import réel JSON

```text
Ajoute une commande d’import réel du JSON vers PostgreSQL. Elle doit créer une entrée migration_runs, rattacher toutes les données à une organization et une shop cibles, insérer dans app_entities, et produire un résumé. Prévois un échec propre et traçable.
```

### Prompt 15 — Validation migration

```text
Ajoute une commande de validation post-migration qui compare les volumes du JSON source avec les lignes app_entities par entity_type. Signale les écarts, doublons de legacy_id, lignes sans organization_id, et lignes sans shop_id.
```

### Prompt 16 — Tests auth

```text
Ajoute des tests ou scripts de vérification pour les cas suivants : route sans session, session invalide, session expirée, utilisateur valide. Utilise les conventions de test existantes du projet si elles existent.
```

### Prompt 17 — Tests isolation organisation

```text
Ajoute des tests d’isolation avec deux utilisateurs, deux organisations et deux boutiques. Vérifie qu’un utilisateur A ne peut pas lire les données de l’organisation B, même en envoyant explicitement l’id de B.
```

### Prompt 18 — Tests isolation boutique

```text
Ajoute des tests d’isolation boutique. Vérifie qu’un utilisateur ne peut pas accéder à une boutique qui n’appartient pas à son organisation, ni créer des données dans cette boutique.
```

### Prompt 19 — Tests objets métier croisés

```text
Ajoute des tests pour empêcher lecture, modification et suppression d’un objet app_entities appartenant à une autre organisation ou boutique. Vérifie aussi que l’objet interdit n’est pas modifié en base.
```

### Prompt 20 — Audit minimal

```text
Si la table audit_events a été validée, ajoute une journalisation minimale des connexions, refus d’accès tenant, créations, modifications et suppressions. Sinon, ne fais rien et explique ce qui manque comme décision.
```

### Prompt 21 — Mode rollback lecture JSON

```text
Ajoute ou documente un mécanisme de rollback permettant de repasser temporairement la lecture sur le JSON local si PostgreSQL est désactivé. Ne permets pas de double écriture non contrôlée.
```

### Prompt 22 — Checklist bêta

```text
Crée une checklist de lancement bêta privée : création organisation, création boutique, création owner, import JSON, validation migration, tests d’isolation, backup PostgreSQL, vérification des sessions. Ne code pas de nouvelle fonctionnalité.
```

## 9. Recommandation de séquencement pour Codex

Ordre conseillé des prompts :

1. Prompt 1 — Inventaire du projet ;
2. Prompt 2 — Inventaire du JSON ;
3. Prompt 3 — Proposition schéma SQL ;
4. validation humaine lundi ;
5. Prompt 4 — Migrations SQL ;
6. Prompt 5 — Configuration PostgreSQL ;
7. Prompt 6 — Couche database ;
8. Prompt 7 — Analyse auth ;
9. validation humaine lundi si l’authentification n’est pas encore tranchée ;
10. Prompt 8 — Auth minimale ;
11. Prompt 9 — Contexte tenant ;
12. Prompt 10 — Abstraction état ;
13. Prompt 13 — Dry-run migration ;
14. Prompt 14 — Import réel JSON ;
15. Prompt 15 — Validation migration ;
16. Prompt 11 — Lecture PostgreSQL ;
17. Prompt 12 — Écriture PostgreSQL ;
18. Prompt 16 — Tests auth ;
19. Prompt 17 — Tests isolation organisation ;
20. Prompt 18 — Tests isolation boutique ;
21. Prompt 19 — Tests objets métier croisés ;
22. Prompt 20 — Audit minimal si validé ;
23. Prompt 21 — Rollback lecture JSON ;
24. Prompt 22 — Checklist bêta.

## 10. Synthèse

Le chemin le plus sûr est :

1. ne pas normaliser trop tôt les données métier inconnues ;
2. introduire d’abord identité, organisation, boutique et sessions ;
3. migrer le JSON dans une table `app_entities` en `jsonb` ;
4. forcer tous les accès via `organization_id` et `shop_id` côté backend ;
5. tester agressivement les accès croisés ;
6. conserver le JSON source comme filet de sécurité ;
7. reporter paiement et permissions complexes ;
8. valider lundi les décisions structurantes avant codage massif.
