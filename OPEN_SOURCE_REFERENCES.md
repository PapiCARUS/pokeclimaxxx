# Open Source References

Date : 2026-07-11.

## Méthode

Sources : GitHub, sites officiels, pages de documentation. L’activité récente est estimée à partir des releases/updates visibles publiquement le 2026-07-11. Vérifier à nouveau avant toute intégration.

## ERP et workflows métier

### ERPNext

- URL : https://github.com/frappe/erpnext
- Licence : GPL/AGPL selon fichiers et versions ; vérifier précisément avant réutilisation.
- Stack : Python, Frappe Framework, MariaDB, JavaScript.
- Activité récente : dépôt très actif, release récente visible en juillet 2026.
- Qualité du code : projet mature, très large, architecture framework spécifique.
- Parties à étudier : stock ledger, items, sales invoices, permissions, dashboards, workflows de documents.
- Risques : licence copyleft forte ; ne pas copier de code sans analyse juridique.
- Intérêt concret : comprendre profondeur ERP et workflows stock/vente.

### Odoo Community

- URL : https://github.com/odoo/odoo
- Licence : LGPLv3 pour Community ; modules Enterprise séparés.
- Stack : Python, PostgreSQL, JavaScript.
- Activité récente : très actif.
- Parties à étudier : inventory, products, kanban/list/form views, actions serveur.
- Risques : architecture très spécifique, complexité élevée.
- Intérêt : patterns ERP éprouvés, mais à simplifier fortement.

### Dolibarr

- URL : https://github.com/Dolibarr/dolibarr
- Licence : GPL.
- Stack : PHP, MySQL/MariaDB.
- Activité : projet historique actif.
- Parties à étudier : modules PME, factures, produits, tiers.
- Risques : stack différente, UX moins moderne.
- Intérêt : workflows petites entreprises et simplicité relative.

## Inventory management

### InvenTree

- URL : https://github.com/inventree/InvenTree
- Licence : MIT.
- Stack : Python/Django, Vue/TypeScript selon versions.
- Activité : projet open source actif.
- Parties à étudier : stock items, part categories, locations, stock movements, barcode workflows.
- Risques : orienté composants/stock industriel plus que cartes/marketplaces.
- Intérêt : excellent modèle mental stock/mouvements/localisations.

### Snipe-IT

- URL : https://github.com/snipe/snipe-it
- Licence : AGPL-3.0.
- Stack : PHP/Laravel.
- Activité : très actif.
- Parties à étudier : assets, checkout/checkin, audit, history.
- Risques : licence AGPL ; domaine asset management différent.
- Intérêt : historique d’activité et traçabilité.

### PartKeepr

- URL : https://github.com/partkeepr/PartKeepr
- Licence : GPL.
- Stack : PHP/Symfony, JS.
- Activité : vérifier, projet plus ancien.
- Parties à étudier : composants, stock, catégories.
- Risques : maintenance incertaine.
- Intérêt : idées de catégorisation stock.

## Seller dashboards / admin panels

### CoreUI React Admin Template

- URL : https://github.com/coreui/coreui-free-react-admin-template
- Licence : MIT.
- Stack : React.
- Activité : maintenu commercialement/open source.
- Parties à étudier : layouts dashboard, sidebar, charts, tables.
- Risques : template générique, peu de workflows métier.
- Intérêt : structure dashboard propre.

### Mantis Free React Admin Template

- URL : https://github.com/codedthemes/mantis-free-react-admin-template
- Licence : MIT indiquée dans la page.
- Stack : React, Material UI.
- Activité : vérifier avant usage.
- Parties à étudier : composants admin, cards KPI, menus.
- Risques : look template, dépendance MUI.
- Intérêt : inspiration UI, pas logique métier.

### Flowbite Admin Dashboard

- URL : https://github.com/themesberg/flowbite-admin-dashboard
- Licence : vérifier dépôt.
- Stack : Tailwind CSS, Flowbite.
- Activité : projet template.
- Parties à étudier : CRUD layouts, modals, drawers, charts, tables.
- Risques : template visuel plus que produit.
- Intérêt : patterns Tailwind admin.

### Metabase

- URL : https://github.com/metabase/metabase
- Licence : AGPL/commercial selon édition ; vérifier.
- Stack : Clojure, React.
- Activité : très actif.
- Parties à étudier : dashboards, questions, filters, drill-down, embedding.
- Risques : licence, complexité, domaine BI.
- Intérêt : reporting et dashboard KPI.

## Card collection managers

### PokeTrax

- URL : https://poketrax.github.io/PokeTrax/ et dépôt lié depuis le site.
- Licence : vérifier dépôt.
- Stack : application desktop selon projet.
- Activité : vérifier avant usage.
- Parties à étudier : collection Pokémon, prix, suivi cartes.
- Risques : domaine collection perso, pas ERP vendeur.
- Intérêt : base cartes et visualisation collection.

### TCG Pocket Collection Tracker

- URL : https://github.com/marcelpanse/tcg-pocket-collection-tracker
- Licence : vérifier dépôt.
- Stack : web app moderne.
- Activité récente : visible dans résultats GitHub.
- Parties à étudier : collection tracking, packs, trades, privacy-first.
- Risques : focalisé Pokémon Pocket, pas multi-marketplace.
- Intérêt : UX collection mobile/communautaire.

### Card Collection Manager 2

- URL : https://github.com/sebastiandine/Card-Collection-Manager-2
- Licence : vérifier dépôt.
- Stack : à vérifier.
- Activité : incertaine.
- Parties à étudier : gestion images de cartes, collection large.
- Risques : maintenance incertaine.
- Intérêt : besoins de base galerie/image.

### Sports Card Tracker

- URL : https://github.com/Collectors-Playbook/sports-card-tracker
- Licence : vérifier dépôt.
- Stack : React, TypeScript, technologies web modernes selon README visible.
- Activité : résultat récent.
- Parties à étudier : analytics, reporting, eBay integration, collection cards.
- Risques : vérifier licence et qualité avant usage.
- Intérêt : proche cartes + analytics vendeur.

## Marketplace analytics

### Plausible Analytics

- URL : https://github.com/plausible/analytics
- Licence : AGPL.
- Stack : Elixir, Phoenix, ClickHouse/PostgreSQL selon versions.
- Activité : actif.
- Parties à étudier : dashboards analytiques simples, filtres période, métriques.
- Risques : licence AGPL, domaine web analytics.
- Intérêt : simplicité KPI et reporting.

### PostHog

- URL : https://github.com/PostHog/posthog
- Licence : MIT/enterprise selon composants ; vérifier.
- Stack : Python, TypeScript, ClickHouse.
- Activité : très actif.
- Parties à étudier : feature flags, analytics, dashboards, events.
- Risques : très large, infra lourde.
- Intérêt : event tracking et feature flags.

## Multi-tenant SaaS starters / architecture

### Nile Auth

- URL : https://github.com/niledatabase/nile-auth
- Licence : vérifier dépôt.
- Stack : Postgres, React components selon README visible.
- Activité : projet récent.
- Parties à étudier : auth B2B multi-tenant, tenants, sessions, org/user model.
- Risques : ne pas intégrer sans valider compatibilité backend natif.
- Intérêt : modèle auth tenant.

### Vercel Platforms Starter Kit

- URL : https://github.com/vercel/platforms
- Licence : vérifier dépôt.
- Stack : Next.js, Vercel, multi-tenant domains.
- Activité : maintenu par Vercel/communauté.
- Parties à étudier : isolation par tenant, domaines, routing.
- Risques : très orienté Next/Vercel, migration architecture.
- Intérêt : concepts multi-tenant web.

### BoxyHQ SaaS Starter / Jackson

- URL : https://github.com/boxyhq/saas-starter-kit et https://github.com/boxyhq/jackson
- Licence : vérifier dépôt.
- Stack : Next.js/Node selon projet.
- Parties à étudier : SSO, enterprise SaaS, org model.
- Risques : trop enterprise pour bêta.
- Intérêt : anticiper auth avancée plus tard.

### Multi-tenant Persistence for SaaS

- URL : https://github.com/vmware-labs/multi-tenant-persistence-for-saas
- Licence : vérifier dépôt.
- Stack : Java/Postgres selon README.
- Parties à étudier : abstraction multi-tenant, isolation, IAM integration.
- Risques : stack différente.
- Intérêt : réflexion architecture data isolation.

## Mobile dashboards

### AppFlowy

- URL : https://github.com/AppFlowy-IO/AppFlowy
- Licence : AGPL.
- Stack : Flutter, Rust.
- Activité : actif.
- Parties à étudier : vues base de données, mobile/desktop, offline/local-first.
- Risques : licence, stack différente.
- Intérêt : mobile/desktop data views.

### Outline

- URL : https://github.com/outline/outline
- Licence : BSL/Business Source License selon versions ; vérifier.
- Stack : Node/React.
- Parties à étudier : sidebar, search, collaboration, settings.
- Risques : licence non permissive.
- Intérêt : navigation et app SaaS propre.

## Références à ne pas copier directement

- Templates admin sans logique métier : utiles pour layout, pas pour workflows.
- Projets AGPL/GPL : étudier les idées, éviter copie de code sans validation juridique.
- Starters Next.js : utiles conceptuellement, mais migration lourde depuis Node HTTP natif.

## Top références à étudier en priorité

1. ERPNext — profondeur ERP stock/vente.
2. Odoo — patterns list/form/kanban et inventaire.
3. InvenTree — modèle stock/mouvements.
4. Metabase — dashboards et filtres analytiques.
5. Sports Card Tracker — domaine cartes + analytics.
6. TCG Pocket Collection Tracker — collection mobile/cartes.
7. Nile Auth — auth multi-tenant B2B.
8. Vercel Platforms — concepts tenants/domaines.
9. CoreUI/Mantis — layouts admin uniquement.
10. Plausible/PostHog — event analytics et feature flags.
