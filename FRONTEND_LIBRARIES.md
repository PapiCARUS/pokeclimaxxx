# Frontend Libraries Research

Date : 2026-07-11.

## Hypothèse de compatibilité

Le frontend actuel est HTML/JavaScript. Les bibliothèques React ne sont donc pas compatibles sans migration ou îlot React. Les recommandations distinguent :

- utilisable sans framework ;
- utilisable si migration progressive vers React ;
- à tester seulement ;
- à éviter pour le moment.

## Synthèse rapide

| Besoin | Bibliothèque | Recommandation |
| --- | --- | --- |
| Design system sans framework | Shopify Polaris Web Components | Tester |
| Primitives accessibles React | Radix UI | Utiliser si React |
| Composants copiables React | shadcn/ui | Tester si React/Tailwind |
| Tableaux | TanStack Table | Utiliser si React/Vue/Svelte ou adapter plus tard |
| Graphiques | Recharts | Utiliser si React ; sinon Chart.js ou ECharts |
| Formulaires | React Hook Form | Utiliser si React |
| Validation | Zod | Utiliser côté frontend/backend si TS/JS moderne |
| Notifications | Sonner | Tester si React ; sinon Toastify/maison |
| Modales | Radix Dialog | Utiliser si React |
| Drag and drop | dnd-kit | Utiliser si React |
| Galerie/lightbox | PhotoSwipe | Utiliser/tester sans framework |
| Dates | date-fns | Utiliser |
| Accessibilité | axe-core / Playwright axe | Utiliser |
| Tests frontend | Playwright | Utiliser |
| Screenshots | Playwright | Utiliser |
| PDF | Playwright PDF / pdf-lib | Tester selon besoin |
| CSV | PapaParse | Utiliser/tester |
| Responsive | CSS natif + container queries | Utiliser |

## Design system et composants UI

### Shopify Polaris Web Components

- Source : https://shopify.dev/docs/api/app-home/web-components
- Rôle : composants web alignés sur un admin commerce.
- Maturité/activité : Shopify a annoncé un Polaris unifié basé sur Web Components utilisable avec ou sans framework : https://www.shopify.com/partners/blog/polaris-unified-and-for-the-web
- Taille/complexité : moyenne ; dépend d’un style Shopify.
- Avantages : compatible avec HTML/JS, patterns commerce, accessibilité pensée.
- Inconvénients : look Shopify, risque de dépendance visuelle externe.
- Compatibilité : bonne pour frontend sans framework.
- Recommandation : tester sur un écran prototype, ne pas adopter aveuglément.

### Radix UI

- Source : https://www.radix-ui.com/ et https://github.com/radix-ui/primitives
- Rôle : primitives accessibles non stylées pour React.
- Maturité/activité : maintenu par WorkOS, MIT, largement adopté.
- Taille/complexité : modulaire.
- Avantages : accessibilité, modales, menus, popovers, select.
- Inconvénients : React uniquement.
- Compatibilité : nécessite migration ou îlots React.
- Recommandation : utiliser si React est choisi.

### shadcn/ui

- Source : https://ui.shadcn.com/ et https://github.com/shadcn-ui/ui
- Rôle : composants copiables/personnalisables, souvent Radix + Tailwind.
- Maturité/activité : très actif ; GitHub indique release récente en juillet 2026.
- Taille/complexité : faible runtime, mais impose discipline Tailwind/design tokens.
- Avantages : contrôle du code, nombreux composants admin modernes.
- Inconvénients : pas une dépendance classique ; nécessite React/Tailwind et maintenance interne.
- Compatibilité : pas compatible direct HTML/JS actuel.
- Recommandation : tester seulement si une migration React/Tailwind est décidée.

### GitHub Primer

- Source : https://primer.style/
- Rôle : design system mature pour interfaces denses.
- Maturité : utilisé par GitHub.
- Avantages : composants et guidelines accessibles, densité professionnelle.
- Inconvénients : peut donner un aspect GitHub si copié trop directement.
- Compatibilité : CSS utilisable, React selon choix.
- Recommandation : excellente référence de design, adoption technique à tester.

## Tableaux

### TanStack Table

- Sources : https://tanstack.com/table/latest/docs/installation et https://github.com/TanStack/table/releases
- Rôle : moteur headless de tables/datagrids.
- Maturité/activité : très actif ; releases v9 beta visibles en 2026, v8 stable historiquement répandue.
- Taille/complexité : moyenne à élevée selon features.
- Avantages : tri, filtres, pagination, colonnes, contrôle total du markup.
- Inconvénients : headless ; nécessite construire l’UI ; versions beta à éviter en production.
- Compatibilité : surtout frameworks modernes ; pas idéal en pur HTML/JS actuel.
- Recommandation : utiliser v8 stable si migration React ; éviter v9 beta en bêta ERP.

## Graphiques

### Recharts

- Sources : https://recharts.github.io/ et https://github.com/recharts/recharts
- Rôle : charts React basés SVG/D3.
- Maturité/activité : actif, version 3.x et discussions/réécritures récentes.
- Avantages : simple, déclaratif, adapté KPI.
- Inconvénients : React uniquement ; performances limitées pour très gros volumes.
- Compatibilité : migration React requise.
- Recommandation : utiliser si React ; sinon Chart.js/ECharts.

### Apache ECharts

- Source : https://echarts.apache.org/
- Rôle : graphiques riches, framework-agnostic.
- Maturité : projet Apache mature.
- Avantages : puissant, nombreux types, utilisable en JS natif.
- Inconvénients : plus lourd que Recharts/Chart.js.
- Compatibilité : bonne avec HTML/JS actuel.
- Recommandation : tester pour rapports avancés.

### Chart.js

- Source : https://www.chartjs.org/
- Rôle : graphiques simples canvas.
- Maturité : mature.
- Avantages : facile, compatible JS natif.
- Inconvénients : moins adapté dashboards très personnalisés.
- Compatibilité : très bonne.
- Recommandation : utiliser pour bêta simple.

## Formulaires et validation

### React Hook Form

- Source : https://react-hook-form.com/
- Rôle : gestion formulaires React.
- Maturité : mature et très utilisé.
- Avantages : performant, flexible.
- Inconvénients : React uniquement.
- Recommandation : utiliser si React.

### Zod

- Source : https://zod.dev/
- Rôle : validation de schémas TypeScript/JavaScript.
- Maturité : mature.
- Avantages : partage possible frontend/backend, messages clairs.
- Inconvénients : adoption TS idéale mais utilisable en JS.
- Compatibilité : bonne.
- Recommandation : utiliser/tester, surtout pour API et imports.

## Notifications, modales, bottom sheets

### Sonner

- Source : https://sonner.emilkowal.ski/
- Rôle : toasts React.
- Avantages : moderne, simple.
- Inconvénients : React.
- Recommandation : tester si React.

### Radix Dialog / Drawer patterns

- Source : https://www.radix-ui.com/primitives
- Rôle : modales, popovers, menus accessibles.
- Recommandation : utiliser si React.

### Shoelace

- Source : https://shoelace.style/
- Rôle : web components UI framework-agnostic.
- Avantages : compatible HTML/JS, composants accessibles.
- Inconvénients : style à adapter.
- Recommandation : tester pour modales, drawers, selects sans migration React.

## Drag and drop

### dnd-kit

- Source : https://dndkit.com/
- Rôle : drag and drop React moderne.
- Avantages : flexible, accessible comparé aux anciens outils.
- Inconvénients : React.
- Recommandation : utiliser si React pour dashboard widgets/kanban.

### SortableJS

- Source : https://sortablejs.github.io/Sortable/
- Rôle : drag and drop listes en JS natif.
- Avantages : compatible actuel.
- Inconvénients : moins aligné avec frameworks modernes.
- Recommandation : tester uniquement si besoin immédiat sans React.

## Galerie d’images et lightbox

### PhotoSwipe

- Source : https://photoswipe.com/
- Rôle : galerie/lightbox framework-agnostic.
- Avantages : mature, performant, mobile-friendly.
- Inconvénients : intégration à styliser.
- Compatibilité : bonne.
- Recommandation : utiliser/tester pour Base cartes.

## Dates

### date-fns

- Source : https://date-fns.org/
- Rôle : manipulation dates.
- Avantages : modulaire, simple.
- Inconvénients : gestion timezone complexe à traiter séparément.
- Recommandation : utiliser.

### Day.js

- Source : https://day.js.org/
- Rôle : alternative légère à Moment.
- Recommandation : tester si API préférée ; ne pas cumuler avec date-fns.

## Accessibilité

### axe-core

- Source : https://github.com/dequelabs/axe-core
- Rôle : moteur de tests accessibilité.
- Avantages : standard de fait.
- Recommandation : utiliser avec Playwright.

## Tests frontend et screenshots

### Playwright

- Source : https://playwright.dev/
- Rôle : tests end-to-end, visuels, screenshots.
- Maturité : très actif.
- Avantages : multi-browser, screenshots, traces.
- Inconvénients : nécessite setup CI.
- Compatibilité : excellente.
- Recommandation : utiliser.

### Vitest

- Source : https://vitest.dev/
- Rôle : tests unitaires frontend JS/TS.
- Recommandation : utiliser si build moderne Vite/React ; sinon attendre.

## PDF/CSV

### PapaParse

- Source : https://www.papaparse.com/
- Rôle : parsing/génération CSV.
- Avantages : mature, simple.
- Recommandation : utiliser/tester pour imports/exports.

### pdf-lib

- Source : https://pdf-lib.js.org/
- Rôle : création/modification PDF.
- Avantages : JS pur.
- Inconvénients : layout complexe manuel.
- Recommandation : tester pour documents simples.

### Playwright PDF

- Source : https://playwright.dev/docs/api/class-page#page-pdf
- Rôle : générer PDF depuis HTML.
- Avantages : rendu fidèle.
- Inconvénients : dépend Chromium côté serveur.
- Recommandation : tester pour rapports/factures plus tard.

## Responsive mobile

- Recommandation : CSS natif, container queries, media queries, bottom navigation spécifique.
- Éviter : transformer les tableaux desktop en scroll horizontal mobile comme solution principale.

## Bibliothèques à éviter pour l’instant

- Gros frameworks admin complets si non alignés au produit.
- Tables/datagrids enterprise payants avant validation des besoins.
- Plusieurs libs de dates/charts simultanément.
- Dépendances React si aucune décision de migration frontend n’est validée.
