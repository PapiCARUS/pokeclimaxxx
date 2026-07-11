# Design Patterns and Anti-Patterns — ERP Climax

## Bonnes pratiques récurrentes

1. **Densité adaptée au métier** : Stripe, Retool, Shopify et Cardmarket montrent que les utilisateurs opérationnels acceptent une forte densité quand elle accélère la décision.
2. **Drill-down systématique** : chaque KPI doit mener à une liste filtrée ou un rapport.
3. **Panneau détail** : Linear, HubSpot et Stripe évitent de perdre le contexte liste.
4. **Filtres persistants** : Shopify, GitHub et Metabase rendent les vues réutilisables.
5. **Actions groupées** : indispensables pour stock et ventes.
6. **Statuts lisibles** : badges sobres avec texte, pas uniquement couleur.
7. **Recherche globale + locale** : recherche globale pour navigation, recherche locale pour tables.
8. **Hiérarchie typographique fine** : peu de tailles, beaucoup de poids/contrastes subtils.
9. **Mobile spécifique** : Revolut, Square, Shopify POS et Collectr ne sont pas des desktops miniatures.
10. **États vides actionnables** : GitHub/Stripe orientent vers la prochaine action.

## Anti-patterns fréquents et alternatives

### 1. Grands blocs vides

- Exemple : dashboard avec 4 grandes cards occupant tout l’écran mais peu d’information.
- Problème : impression de produit vide ou généré par IA.
- Impact : baisse de confiance, perte de temps.
- Alternative : cards compactes + table/action feed + vrais liens de drill-down.

### 2. Cartes KPI sans hiérarchie

- Exemple : toutes les cartes ont même taille, même couleur, même poids.
- Problème : aucune priorité.
- Impact : l’utilisateur ne sait pas quoi regarder.
- Alternative : 1 KPI principal, 3-5 secondaires, delta et période visibles.

### 3. Arrondis excessifs

- Exemple : cards arrondies 24-32 px dans un ERP.
- Problème : esthétique jouet/mobile générique.
- Impact : manque de sérieux.
- Alternative : rayons 6-12 px selon composant ; tables plus angulaires.

### 4. Dégradés inutiles

- Exemple : header violet/bleu sans fonction.
- Problème : langage marketing, pas outil professionnel.
- Impact : perception IA/template.
- Alternative : couleur d’accent utilisée pour statut/action importante.

### 5. Pictogrammes décoratifs

- Exemple : icône sur chaque card KPI sans rôle.
- Problème : bruit visuel.
- Impact : fatigue cognitive.
- Alternative : icônes uniquement pour navigation, statut ou action.

### 6. Dashboards trop marketing

- Exemple : hero dashboard avec phrases inspirantes et graphiques décoratifs.
- Problème : ne sert pas la journée vendeur.
- Impact : abandon du dashboard.
- Alternative : tâches à traiter, ventes, marge, stock dormant, alertes.

### 7. Trop de blanc

- Exemple : Vercel-like appliqué à une page stock.
- Problème : peu d’objets visibles.
- Impact : scroll excessif.
- Alternative : densité table compacte sur pages opérationnelles.

### 8. Mauvaise densité

- Exemple : table lignes 72 px avec 4 colonnes visibles.
- Problème : gaspillage d’espace.
- Impact : impossible de comparer les cartes/prix.
- Alternative : lignes 36-52 px, colonnes alignées, toolbar compacte.

### 9. Tableaux illisibles

- Exemple : colonnes non alignées, montants mélangés, statut couleur seule.
- Problème : erreurs de lecture.
- Impact : erreurs de prix, stock, expédition.
- Alternative : alignement numérique à droite, statuts textuels, colonnes prioritaires fixes.

### 10. Mobile réduit au desktop miniaturisé

- Exemple : sidebar desktop cachée dans hamburger et table complète scroll horizontal.
- Problème : interactions lentes.
- Impact : mobile inutilisable en live ou déplacement.
- Alternative : bottom nav, listes compactes, actions rapides, bottom sheets.

### 11. Filtres enterrés

- Exemple : filtres seulement dans une modale complexe.
- Problème : état de la vue invisible.
- Impact : confusion sur les résultats.
- Alternative : chips actifs visibles, vues sauvegardées, reset clair.

### 12. États vides illustratifs mais non utiles

- Exemple : illustration 3D et texte `Aucune donnée pour le moment`.
- Problème : pas de prochaine étape.
- Impact : blocage onboarding.
- Alternative : `Importer ton stock`, `Ajouter une carte`, `Créer un live`.

### 13. Graphiques décoratifs

- Exemple : donut 3 segments sans valeur métier.
- Problème : occupe de la place sans décision.
- Impact : dashboard ignoré.
- Alternative : graphiques reliés à actions : stock dormant, marge par plateforme, ventes à expédier.

### 14. Couleurs de badges incohérentes

- Exemple : vert pour `vendu`, bleu pour `payé`, violet pour `expédié` sans système.
- Problème : apprentissage difficile.
- Impact : erreurs opérationnelles.
- Alternative : système de statuts documenté : neutre, info, succès, warning, danger.

### 15. Navigation trop plate

- Exemple : 20 entrées dans une sidebar.
- Problème : aucune architecture métier.
- Impact : perte d’orientation.
- Alternative : groupes métier et navigation secondaire par page.

## Patterns à adopter pour ERP Climax

- Sidebar métier groupée.
- Top bar utile avec boutique active, recherche, action rapide.
- Tables denses avec drawer détail.
- KPI cards cliquables.
- Vues sauvegardées pour Stock/Ventes/Rapports.
- Mobile bottom navigation distincte.
- Galerie cartes hybride avec données compactes.
- État vide actionnable.
- Système de statuts sobre.
- Reporting orienté décisions vendeur.
