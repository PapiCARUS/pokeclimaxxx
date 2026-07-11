# Component Opportunities — ERP vendeur

Date : 2026-07-11.

## Matrice d’opportunités

| Idée | Valeur utilisateur | Difficulté | Priorité | Dépendances | Desktop/Mobile | Timing |
| --- | --- | --- | --- | --- | --- | --- |
| Filtres enregistrés | Retrouver rapidement les vues de stock, ventes, lives | Moyenne | Haute | modèle filtres, stockage utilisateur | Desktop puis mobile | Maintenant |
| Densité réglable | Adapter l’interface aux gros catalogues | Faible à moyenne | Haute | design tokens CSS | Desktop | Maintenant |
| Recherche globale | Accès rapide cartes, ventes, dépenses, paramètres | Moyenne | Haute | indexation serveur, permissions | Desktop + mobile | Maintenant/après bêta |
| Palette de commandes | Productivité avancée | Moyenne | Moyenne | recherche, raccourcis | Desktop | Après bêta |
| Vues table/liste/galerie | Adapter stock et base cartes aux tâches | Moyenne | Haute | composants table/galerie | Desktop + mobile partiel | Maintenant |
| Dashboard personnalisable | Suivi KPI pertinent par vendeur | Moyenne à élevée | Moyenne | widgets, préférences utilisateur | Desktop | Après bêta |
| Alertes intelligentes | Stock faible, marge faible, live non rentable | Moyenne | Haute | règles métier, données propres | Desktop + mobile | Après bêta |
| Centre de notifications | Centraliser alertes et actions | Moyenne | Moyenne | audit/events | Desktop + mobile | Après bêta |
| Historique d’activité | Confiance, audit, debug multi-utilisateur | Moyenne | Haute SaaS | audit_events | Desktop | Maintenant/après bêta |
| Onboarding progressif | Réduire friction première utilisation | Faible à moyenne | Haute | checklist état | Desktop | Maintenant |
| Import assistant | Sécuriser migration CSV/JSON | Moyenne | Haute | validation import | Desktop | Maintenant |
| Actions bulk | Modifier/pricer/tagger plusieurs articles | Moyenne | Haute | tables robustes | Desktop | Maintenant |
| Colonnes configurables | Adapter stock/ventes aux vendeurs | Moyenne | Moyenne | préférences utilisateur | Desktop | Après bêta |
| Panneau latéral détail | Éditer sans perdre la liste | Moyenne | Haute | routing/état UI | Desktop | Maintenant |
| Bottom navigation mobile | Accès rapide mobile | Faible | Haute mobile | direction mobile | Mobile | Après bêta |
| Bottom sheets | Filtres/actions mobiles ergonomiques | Moyenne | Haute mobile | lib UI mobile | Mobile | Après bêta |
| Galerie Base cartes | Recherche visuelle et collection | Moyenne | Haute | images, lightbox | Desktop + mobile | Maintenant |
| Lightbox image | Voir état/détails carte | Faible | Moyenne | images | Desktop + mobile | Maintenant |
| Quick add vente/dépense | Réduire friction de saisie | Moyenne | Haute | formulaires courts | Desktop + mobile | Maintenant |
| Vues objectifs | Suivre objectifs CA/marge/stock | Moyenne | Moyenne | module objectifs | Desktop | Après bêta |
| Raccourcis clavier | Productivité power users | Faible à moyenne | Moyenne | documentation, command palette | Desktop | Après bêta |
| États vides actionnables | Guider nouveaux vendeurs | Faible | Haute | contenu UX | Desktop + mobile | Maintenant |
| Templates de rapports | Rapports utiles sans configuration | Moyenne | Haute | données ventes/dépenses | Desktop | Après bêta |
| Export CSV/PDF | Besoin compta/partage | Moyenne | Haute | rapports, permissions | Desktop | Après bêta |
| Sélecteur organisation/boutique | Préparer SaaS multi-tenant | Moyenne | Haute SaaS | auth, modèle tenant | Desktop + mobile | Maintenant |

## Top 10 à fort impact immédiat

1. Filtres enregistrés.
2. Densité réglable.
3. Vues table/liste/galerie.
4. Panneau latéral détail.
5. Actions bulk.
6. Recherche globale.
7. Onboarding progressif.
8. Import assistant.
9. Galerie Base cartes.
10. États vides actionnables.

## À faire maintenant

- Définir tokens visuels et densités.
- Créer spécification des tableaux, filtres et vues.
- Spécifier la galerie Base cartes.
- Spécifier empty states et onboarding.
- Préparer sélecteur boutique/organisation même si la bêta reste simple.

## Après bêta

- Dashboard personnalisable.
- Alertes intelligentes.
- Centre de notifications.
- Command palette.
- Colonnes configurables persistées.
- Exports avancés.

## Plus tard

- Automatisations complexes.
- Facturation SaaS.
- Thème sombre complet.
- Marketplace d’intégrations.
