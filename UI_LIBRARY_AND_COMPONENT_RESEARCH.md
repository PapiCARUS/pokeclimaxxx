# UI Library and Component Research — ERP Climax

## Principe d’évaluation

Critères : URL, activité récente apparente, popularité, taille, maturité, documentation, dépendances, compatibilité JavaScript pur, compatibilité avec l’architecture actuelle Node HTTP natif + frontend HTML/JS, avantages, risques, intérêt concret.

## Tables et data grids

### AG Grid

- URL : https://www.ag-grid.com/
- Activité/popularité : très populaire, produit mature, éditions Community/Enterprise.
- Documentation : excellente.
- JS pur : oui, utilisable sans framework.
- Avantages : tri, filtre, édition, virtualisation, colonnes, performances.
- Risques : richesse complexe, licence Enterprise pour fonctions avancées.
- Intérêt Climax : très fort pour Stock, Ventes, Dépenses, Base cartes.

### TanStack Table

- URL : https://tanstack.com/table
- Activité : très active dans l’écosystème web.
- JS pur : headless, surtout utilisé avec frameworks.
- Avantages : contrôle total, léger conceptuellement.
- Risques : demande beaucoup d’implémentation UI.
- Intérêt Climax : moyen si frontend reste pur HTML/JS.

### Grid.js

- URL : https://gridjs.io/
- Activité : bibliothèque simple.
- JS pur : oui.
- Avantages : légère, facile, tables basiques.
- Risques : limites pour ERP dense.
- Intérêt Climax : bon pour bêta simple, limité long terme.

### Tabulator

- URL : https://tabulator.info/
- JS pur : oui.
- Avantages : riche, édition, filtres, pagination, data trees.
- Risques : look à personnaliser.
- Intérêt Climax : très intéressant pour architecture actuelle.

### Handsontable

- URL : https://handsontable.com/
- Maturité : élevée.
- Avantages : expérience tableur.
- Risques : licence, UX tableur pas toujours adaptée ERP.
- Intérêt Climax : utile si édition massive stock.

### DataTables

- URL : https://datatables.net/
- Maturité : très élevée.
- JS pur/jQuery : dépend de jQuery.
- Avantages : robuste, répandu.
- Risques : esthétique datée, dépendance jQuery.
- Intérêt Climax : moyen.

## Charts

### Apache ECharts

- URL : https://echarts.apache.org/
- Maturité : élevée.
- JS pur : oui.
- Avantages : puissant, nombreux graphiques.
- Risques : peut produire des dashboards trop chargés.
- Intérêt : fort pour Rapports.

### Chart.js

- URL : https://www.chartjs.org/
- Maturité : élevée.
- JS pur : oui.
- Avantages : simple, populaire.
- Risques : moins BI avancé.
- Intérêt : très bon pour dashboard et rapports simples.

### D3.js

- URL : https://d3js.org/
- Maturité : très élevée.
- JS pur : oui.
- Avantages : liberté totale.
- Risques : coût d’implémentation élevé.
- Intérêt : faible au départ.

### Observable Plot

- URL : https://observablehq.com/plot/
- Avantages : déclaratif, bon pour exploration.
- Risques : intégration produit à évaluer.
- Intérêt : moyen.

## Forms

### FormKit

- URL : https://formkit.com/
- Orientation : surtout Vue.
- Intérêt Climax : faible si JS pur.

### JustValidate

- URL : https://just-validate.dev/
- JS pur : oui.
- Avantages : validation simple.
- Risques : ne fournit pas design complet.
- Intérêt : bon pour formulaires simples.

### Parsley

- URL : https://parsleyjs.org/
- Maturité : ancienne.
- Risques : stack datée.
- Intérêt : faible à moyen.

## Date pickers

### Flatpickr

- URL : https://flatpickr.js.org/
- JS pur : oui.
- Avantages : léger, mature, range, time.
- Risques : design à adapter.
- Intérêt : très fort.

### Litepicker

- URL : https://wakirin.github.io/Litepicker/
- JS pur : oui.
- Avantages : range picker léger.
- Intérêt : bon pour rapports.

### Pikaday

- URL : https://pikaday.com/
- Maturité : ancienne.
- Intérêt : faible sauf simplicité.

## Filters et command palette

### Fuse.js

- URL : https://www.fusejs.io/
- JS pur : oui.
- Avantages : fuzzy search locale.
- Intérêt : très fort pour recherche cartes/stock côté client.

### cmdk

- URL : https://cmdk.paco.me/
- Framework : React.
- Intérêt : inspiration UX, faible compatibilité directe.

### kbar

- URL : https://kbar.vercel.app/
- Framework : React.
- Intérêt : inspiration command palette.

## Modals, drawers, bottom sheets

### Micromodal

- URL : https://micromodal.vercel.app/
- JS pur : oui.
- Avantages : accessible, léger.
- Intérêt : fort pour modales simples.

### Shoelace

- URL : https://shoelace.style/
- Web Components : oui.
- Avantages : composants framework-agnostic, drawers, dialogs.
- Risques : adopter un design system externe.
- Intérêt : très fort pour architecture actuelle.

### Floating UI

- URL : https://floating-ui.com/
- JS pur : oui.
- Avantages : positionnement dropdowns/tooltips/popovers.
- Intérêt : très fort.

## Drag and drop

### SortableJS

- URL : https://sortablejs.github.io/Sortable/
- JS pur : oui.
- Avantages : mature, simple.
- Intérêt : fort pour ordre lots Whatnot.

### Dragula

- URL : https://bevacqua.github.io/dragula/
- Maturité : ancienne.
- Intérêt : moyen.

## Lightbox et galeries

### PhotoSwipe

- URL : https://photoswipe.com/
- JS pur : oui.
- Avantages : mature, mobile friendly.
- Intérêt : fort pour cartes.

### GLightbox

- URL : https://biati-digital.github.io/glightbox/
- JS pur : oui.
- Avantages : simple.
- Intérêt : moyen.

## Virtual lists

### Clusterize.js

- URL : https://clusterize.js.org/
- JS pur : oui.
- Avantages : listes longues.
- Risques : projet ancien.
- Intérêt : moyen.

### HyperList

- URL : https://github.com/tbranyen/hyperlist
- JS pur : oui.
- Risques : activité à vérifier.
- Intérêt : faible à moyen.

## Accessibility

### axe DevTools / axe-core

- URL : https://github.com/dequelabs/axe-core
- Avantages : tests accessibilité automatisables.
- Intérêt : fort.

### WAI-ARIA Authoring Practices

- URL : https://www.w3.org/WAI/ARIA/apg/
- Avantages : référence officielle patterns accessibles.
- Intérêt : essentiel pour modales, tabs, combobox.

## Testing et screenshots

### Playwright

- URL : https://playwright.dev/
- Avantages : tests E2E, screenshots, multi-browser.
- Intérêt : très fort pour refonte UI.

### Cypress

- URL : https://www.cypress.io/
- Avantages : E2E mature.
- Intérêt : fort, mais Playwright plus adapté screenshots multi-browser.

### BackstopJS

- URL : https://github.com/garris/BackstopJS
- Avantages : visual regression.
- Intérêt : fort pour éviter régressions UI.

## PDF/CSV export

### Papa Parse

- URL : https://www.papaparse.com/
- JS pur : oui.
- Avantages : CSV robuste.
- Intérêt : fort pour exports/imports.

### SheetJS

- URL : https://sheetjs.com/
- Avantages : Excel/CSV.
- Risques : licence/fonctions à vérifier.
- Intérêt : fort si export Excel.

### jsPDF

- URL : https://github.com/parallax/jsPDF
- Avantages : PDF côté client.
- Risques : mise en page complexe.
- Intérêt : moyen.

## Recommandation technique provisoire

Pour architecture HTML/JS sans framework : AG Grid ou Tabulator pour tables, Chart.js ou ECharts pour charts, Flatpickr pour dates, Fuse.js pour recherche, Shoelace/Floating UI/Micromodal pour overlays, SortableJS pour lots, PhotoSwipe pour cartes, Playwright + axe-core + BackstopJS pour qualité UI.
