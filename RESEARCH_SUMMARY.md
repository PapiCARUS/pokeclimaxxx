# Research Summary — prochaine phase ERP vendeur

Date : 2026-07-11.

## 10 meilleures références UI

1. Shopify Admin / Polaris — meilleure référence commerce/admin marchand. Source : https://shopify.dev/docs/api/app-home/web-components
2. Stripe Dashboard — settings, ressources, recherche, rigueur SaaS. Source : https://docs.stripe.com/dashboard/basics
3. GitHub / Primer — densité, filtres, accessibilité, tables. Source : https://primer.style/
4. Linear — dashboards modulaires, polish, rapidité. Source : https://linear.app/changelog/2025-07-24-dashboards
5. Notion databases — vues table/list/board/gallery/calendar/timeline. Source : https://www.notion.com/help/guides/using-database-views
6. Odoo Inventory — profondeur workflows stock. Source : https://www.odoo.com/documentation/19.0/applications/inventory_and_mrp/inventory.html
7. ERPNext — ERP open source complet et actif. Source : https://github.com/frappe/erpnext
8. Vercel Dashboard — statuts, logs, observabilité, détail ressources. Source : https://vercel.com/docs/deployments
9. Square Dashboard — KPIs vendeurs et reporting simple. Source : https://squareup.com/us/en/point-of-sale/features/dashboard
10. Revolut Business — mobile business rapide et financier. Source : https://www.revolut.com/business/

## 10 bibliothèques les plus utiles

1. `pg` / node-postgres — accès PostgreSQL bas niveau compatible backend natif. Source : https://node-postgres.com/
2. `node-pg-migrate` ou `dbmate` — migrations SQL/PostgreSQL. Source : https://salsita.github.io/node-pg-migrate/
3. Zod — validation API, imports, formulaires. Source : https://zod.dev/
4. Pino — logs JSON performants. Source : https://getpino.io/
5. Playwright — tests E2E, screenshots, smoke tests. Source : https://playwright.dev/
6. TanStack Table — moteur de tables si migration React/framework. Source : https://tanstack.com/table/latest/docs/installation
7. Radix UI — primitives accessibles si React. Source : https://www.radix-ui.com/primitives
8. Shopify Polaris Web Components ou Shoelace — composants web compatibles sans React. Sources : https://shopify.dev/docs/api/app-home/web-components et https://shoelace.style/
9. Chart.js ou Apache ECharts — graphiques compatibles JS actuel. Sources : https://www.chartjs.org/ et https://echarts.apache.org/
10. PhotoSwipe — galerie/lightbox pour Base cartes. Source : https://photoswipe.com/

## 10 projets open source les plus intéressants

1. ERPNext — ERP complet stock/vente. https://github.com/frappe/erpnext
2. Odoo Community — ERP PostgreSQL, vues list/form/kanban. https://github.com/odoo/odoo
3. InvenTree — stock, mouvements, localisations. https://github.com/inventree/InvenTree
4. Metabase — dashboards et BI. https://github.com/metabase/metabase
5. Sports Card Tracker — cartes + analytics. https://github.com/Collectors-Playbook/sports-card-tracker
6. TCG Pocket Collection Tracker — collection cartes mobile/web. https://github.com/marcelpanse/tcg-pocket-collection-tracker
7. Nile Auth — auth multi-tenant B2B. https://github.com/niledatabase/nile-auth
8. Vercel Platforms — multi-tenant concepts. https://github.com/vercel/platforms
9. PostHog — events, feature flags, product analytics. https://github.com/PostHog/posthog
10. CoreUI React Admin Template — layout admin. https://github.com/coreui/coreui-free-react-admin-template

## 10 idées produit à fort impact

1. Filtres enregistrés par module.
2. Densité réglable des tableaux.
3. Vues table/liste/galerie pour stock et base cartes.
4. Panneau latéral de détail/édition.
5. Recherche globale.
6. Actions bulk sur stock/ventes.
7. Onboarding progressif avec checklist.
8. Assistant d’import CSV/JSON.
9. Galerie Base cartes avec lightbox.
10. Historique d’activité préparant le multi-utilisateur.

## 5 choses à éviter

1. Copier une interface premium au détriment de la densité et de la vitesse.
2. Ajouter React/Tailwind/shadcn uniquement pour le style sans décision d’architecture.
3. Installer plusieurs bibliothèques concurrentes pour dates, charts, modales ou tables.
4. Copier du code AGPL/GPL sans validation juridique.
5. Construire billing/facturation SaaS avant auth, tenant isolation, migration PostgreSQL et UX cœur métier.

## Plan de travail recommandé pour lundi

1. Valider la direction visuelle : Dense Pro Commerce + galerie cartes.
2. Décider si le frontend reste HTML/JS court terme ou migre progressivement vers React.
3. Choisir une stratégie composants : CSS maison + web components, ou React + Radix/shadcn.
4. Prioriser les composants UX immédiats : table dense, filtres, panneau détail, galerie, onboarding.
5. Valider la stack backend minimale : `pg`, migrations SQL, Zod, sessions serveur, Pino.
6. Définir les règles de non-régression UX : pas de dépendances lourdes inutiles, accessibilité minimale, responsive distinct.
7. Préparer une PR de spécification UI avant toute PR de code.

## Ordre conseillé avant de reprendre le code

1. Lire `UI_BENCHMARK.md` et sélectionner 5 écrans de référence.
2. Lire `UI_DIRECTION.md` et valider une direction.
3. Lire `FRONTEND_LIBRARIES.md` et trancher framework ou non-framework.
4. Lire `BACKEND_AND_SAAS_LIBRARIES.md` et figer les briques backend minimales.
5. Lire `OPEN_SOURCE_REFERENCES.md` et sélectionner 3 projets à étudier en profondeur.
6. Lire `COMPONENT_OPPORTUNITIES.md` et transformer les idées prioritaires en tickets.
7. Écrire une spécification d’écran pour dashboard, stock, ventes et base cartes.
8. Reprendre le code uniquement après validation de la direction UX et des dépendances.

## Incertitudes à lever

- Accès réel aux interfaces fermées : certaines analyses s’appuient sur docs publiques et pages produit.
- Licences exactes de certains petits projets cartes/templates : vérifier dans chaque dépôt avant réutilisation.
- Choix frontend : rester HTML/JS ou migrer vers React change fortement les recommandations.
- Volumétrie réelle stock/cartes/ventes : nécessaire pour choisir table virtuelle, pagination serveur et stratégie images.
