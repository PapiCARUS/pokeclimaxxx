# UI Visual Reference Board — ERP Climax

## Objectif

Ce document complète la recherche UI existante avec des **références visuelles à ouvrir** avant toute refonte. L’objectif est de ne pas rester au niveau des descriptions textuelles : chaque référence ci-dessous pointe vers une page produit, une galerie, une documentation illustrée, une démo ou un dépôt avec captures permettant d’observer réellement les écrans, la densité, les tableaux, les navigations et les composants.

> Note : ce document évite de recopier ou d’intégrer des captures propriétaires dans le dépôt. Les liens servent de moodboard légal et maintenable. Les captures finales à intégrer dans un outil design devront être collectées manuellement depuis les pages sources, avec attribution interne.

## Comment utiliser ce moodboard

1. Ouvrir les liens par famille.
2. Capturer les écrans pertinents dans un outil de design ou de documentation interne.
3. Annoter chaque capture avec : densité, structure, composants, couleur, typographie, interactions.
4. Ne garder que les références qui résolvent un problème concret de Climax.
5. Refuser les références simplement “jolies” mais non opérationnelles.

## Grille de lecture visuelle

| Critère | Question à poser |
| --- | --- |
| Densité | Combien d’objets utiles sont visibles sans scroll ? |
| Hiérarchie | L’œil comprend-il quoi faire en premier ? |
| Navigation | Le module actif et le contexte sont-ils évidents ? |
| Tables | Les colonnes permettent-elles de comparer vite ? |
| Actions | L’action primaire est-elle visible sans être agressive ? |
| États | Les statuts, erreurs, vides et loaders sont-ils utiles ? |
| Mobile | L’écran est-il repensé pour le tactile ou seulement réduit ? |
| Identité | L’interface a-t-elle une personnalité sans devenir décorative ? |

## Board A — Densité B2B moderne

| Référence visuelle | Lien | À observer | Pertinence Climax |
| --- | --- | --- | --- |
| Linear app screens | https://www.saasui.design/application/linear | sidebar, vues liste, modales, empty states, settings | modèle de densité moderne sans surcharge |
| Linear redesign blog | https://linear.app/blog/how-we-redesigned-the-linear-ui | réduction du bruit, tabs, panels, sidebar | méthode de hiérarchie visuelle à appliquer |
| Linear Page Flows | https://pageflows.com/web/products/linear/ | parcours réels et séquences écran | utile pour transitions et flows |
| GitHub interface | https://github.com/ | listes, labels, tabs, breadcrumbs, activity | très utile pour Base cartes, paramètres, listes |
| GitHub Primer | https://primer.style/ | design system réel utilisé à grande échelle | composants sobres et accessibles |
| Supabase dashboard | https://supabase.com/dashboard | sidebar, table editor, logs, settings | inspiration tables/settings denses |
| Retool templates | https://retool.com/templates | admin panels, dashboards, tables, drawers | forte inspiration outil interne opérationnel |
| Retool dashboard tutorial | https://retool.com/resources/build-your-first-dashboard-in-retool | KPI, charts, table, drawer | modèle dashboard actionnable |

### Conclusion visuelle pour Climax

Cette famille doit guider la structure desktop : sidebar compacte, top bar utile, tables denses, panels de détail. Elle ne doit pas dicter l’identité complète, sinon Climax risque de paraître froid et copié.

## Board B — Finance premium et confiance

| Référence visuelle | Lien | À observer | Pertinence Climax |
| --- | --- | --- | --- |
| Stripe Dashboard support | https://support.stripe.com/topics/dashboard | paiements, disputes, navigation dashboard | rigueur montants/statuts |
| Stripe product | https://stripe.com/ | langage visuel premium, charts, cards | confiance et précision visuelle |
| Stripe visual references | https://refero.design/9-stripe.com | captures web Stripe regroupées | moodboard fintech premium |
| Ramp | https://ramp.com/ | dépenses, cards, tableaux financiers | Dépenses et Objectifs |
| Brex | https://www.brex.com/ | budgets, dépenses, cards premium | direction finance pro |
| Wise Business | https://wise.com/business/ | transactions, soldes, mobile/web | finance accessible |
| Revolut Business | https://www.revolut.com/business/ | mobile-first, comptes, transactions | mobile Climax et dépenses |
| Pennylane | https://www.pennylane.com/ | finance PME française, tableaux | Dépenses/Rapports accessibles |
| QuickBooks | https://quickbooks.intuit.com/ | reporting PME, factures, dépenses | à simplifier pour vendeurs |
| Xero | https://www.xero.com/ | dashboard financier PME | lisibilité comptable légère |

### Conclusion visuelle pour Climax

À reprendre : alignement des montants, statuts sobres, hiérarchie de chiffres, détails transactionnels. À éviter : esthétique fintech trop abstraite ou corporate.

## Board C — E-commerce, POS et seller operations

| Référence visuelle | Lien | À observer | Pertinence Climax |
| --- | --- | --- | --- |
| Shopify Admin | https://www.shopify.com/admin | produits, commandes, analytics, settings | référence majeure pour vendeur |
| Shopify Admin docs | https://shopify.dev/docs/apps/build/admin | intégration au look admin, UI extensions | cohérence d’app marchand |
| Shopify POS | https://www.shopify.com/pos | caisse tactile, grille produits, actions rapides | lives et mobile |
| Square | https://squareup.com/ | POS, catalogue, ventes, dashboard | petits vendeurs et actions simples |
| Lightspeed | https://www.lightspeedhq.com/ | retail, stock, caisse, rapports | stock et ventes professionnelles |
| eBay Seller Hub | https://www.ebay.com/sh/overview | annonces, performance, tâches vendeur | vendeur marketplace multicanal |
| Amazon Seller Central | https://sellercentral.amazon.com/ | inventaire, commandes, performance | densité à étudier mais simplifier |
| Faire | https://www.faire.com/ | marketplace wholesale, catalogue, commandes | marketplace B2B propre |
| Stocky | https://apps.shopify.com/stocky | inventaire, prévision, achats | stock vendeur |
| Zoho Inventory | https://www.zoho.com/inventory/ | articles, commandes, stock | ERP stock classique |

### Conclusion visuelle pour Climax

Cette famille doit fortement influencer Stock, Ventes Vinted et Lives Whatnot. Climax doit adopter la logique opérations/commandes, mais éviter de devenir un clone Shopify.

## Board D — Cartes, collection et marketplace spécialisée

| Référence visuelle | Lien | À observer | Pertinence Climax |
| --- | --- | --- | --- |
| Whatnot | https://www.whatnot.com/ | live selling, flux, lots, enchères | cœur du module Lives Whatnot |
| Vinted | https://www.vinted.com/ | listing photo, vente, statut, messagerie | Ventes Vinted |
| Cardmarket | https://www.cardmarket.com/ | tables d’offres, état, prix, vendeurs | densité cartes/pricing |
| TCGplayer | https://www.tcgplayer.com/ | market price, offres, fiches cartes | pricing cartes et marketplace |
| PriceCharting | https://www.pricecharting.com/ | historique prix, collection value | rapports valeur stock |
| Pokécardex | https://www.pokecardex.com/ | séries, cartes, galerie, checklist | Base cartes Pokémon |
| Collectr | https://getcollectr.com/ | portfolio, scan, valeur collection | mobile carte et valeur stock |
| Ludex | https://www.ludex.com/ | scan, collection, card details | scan/mobile collection |
| eBay card listings | https://www.ebay.com/b/Trading-Card-Games/2536/bn_7116496578 | cards marketplace, prix, filtres | pricing vendeur |
| ALT marketplace | https://www.alt.xyz/ | collection premium, portfolio, cards | direction premium collection |

### Conclusion visuelle pour Climax

C’est la famille qui peut donner une identité propre à Climax. La clé : combiner la galerie et le visuel carte avec la densité professionnelle des tables prix/stock.

## Board E — Analytics et reporting

| Référence visuelle | Lien | À observer | Pertinence Climax |
| --- | --- | --- | --- |
| Metabase | https://www.metabase.com/ | dashboards, filtres, questions, drill-down | Rapports accessibles |
| Metabase GitHub | https://github.com/metabase/metabase | produit open source avec UI réelle | inspiration implementation/UX |
| Looker Studio | https://lookerstudio.google.com/ | filtres, reporting partageable | rapports période/plateforme |
| Tableau | https://www.tableau.com/ | visualisations BI avancées | inspiration, pas copie |
| Power BI | https://powerbi.microsoft.com/ | dashboards enterprise | à simplifier |
| Datadog dashboards | https://www.datadoghq.com/ | dashboards denses, alertes, timelines | alertes/reporting dense |
| Mixpanel | https://mixpanel.com/ | segments, cohorts, funnels | à adapter prudemment |
| Amplitude | https://amplitude.com/ | analytics exploratoire | inspiration filtres/charts |
| Grafana | https://grafana.com/ | panels, time ranges, alertes | densité et périodes |
| Apache Superset | https://superset.apache.org/ | BI open source dense | inspiration dashboards |

### Conclusion visuelle pour Climax

Les rapports doivent rester orientés décision vendeur : marge, stock dormant, dépenses, plateformes rentables. Les références BI sont utiles pour filtres et drill-down, mais risquent de devenir trop abstraites.

## Board F — Open-source UI à inspecter visuellement

| Référence visuelle | Lien | À observer | Pertinence Climax |
| --- | --- | --- | --- |
| ERPNext | https://github.com/frappe/erpnext | ERP réel, stock, formulaires, listes | profondeur ERP |
| Odoo | https://github.com/odoo/odoo | vues liste/kanban/form, POS | ERP mature |
| Dolibarr | https://github.com/Dolibarr/dolibarr | PME, stock, facture | patterns business |
| InvenTree | https://github.com/inventree/InvenTree | inventaire réel, parts, stock movements | Stock Climax |
| Snipe-IT | https://github.com/snipe/snipe-it | assets, statuts, historique | fiches stock |
| Twenty CRM | https://github.com/twentyhq/twenty | CRM moderne, objets, vues | fiches et listes modernes |
| Plane | https://github.com/makeplane/plane | Linear-like open source | navigation/listes |
| Chatwoot | https://github.com/chatwoot/chatwoot | inbox, panels, activité | timelines et side panels |
| Tabler | https://github.com/tabler/tabler | admin UI kit HTML/CSS | composants visuels rapides |
| AdminLTE | https://github.com/ColorlibHQ/AdminLTE | admin dashboard mature | anti-référence partielle |

### Conclusion visuelle pour Climax

Ces références servent à observer des UI réellement implémentées et maintenues. Elles ne doivent pas être copiées visuellement telles quelles, mais elles aident à valider les patterns robustes.

## Board G — Bibliothèques avec démos visuelles à ouvrir

| Composant | Référence | Lien | À observer |
| --- | --- | --- | --- |
| Data grid | AG Grid | https://www.ag-grid.com/example/ | densité, colonnes, filtres, virtualisation |
| Data grid | Tabulator | https://tabulator.info/examples/ | JS pur, tables éditables, pagination |
| Data grid | Grid.js | https://gridjs.io/docs/examples/basic | simplicité table JS |
| Data grid | Handsontable | https://handsontable.com/demo | édition type tableur |
| Charts | Chart.js | https://www.chartjs.org/docs/latest/samples/information.html | charts simples |
| Charts | ECharts | https://echarts.apache.org/examples/en/index.html | dashboards/charts riches |
| Date picker | Flatpickr | https://flatpickr.js.org/examples/ | range date, time picker |
| Modal | Micromodal | https://micromodal.vercel.app/ | modales accessibles simples |
| Components | Shoelace | https://shoelace.style/components/overview | web components framework-agnostic |
| Positioning | Floating UI | https://floating-ui.com/ | menus, tooltips, popovers |
| Drag/drop | SortableJS | https://sortablejs.github.io/Sortable/ | ordre lots/live |
| Lightbox | PhotoSwipe | https://photoswipe.com/ | galerie cartes mobile-friendly |
| Visual tests | Playwright | https://playwright.dev/docs/screenshots | screenshots automatisés |
| Visual regression | BackstopJS | https://github.com/garris/BackstopJS | comparaison visuelle |
| Accessibility | axe-core | https://github.com/dequelabs/axe-core | audits accessibilité |

## Références visuelles par page Climax

### Dashboard

- Stripe Dashboard : structure financière et montants.
- Shopify Analytics : commerce et ventes.
- Square Dashboard : petits vendeurs.
- Ramp : dépenses et alertes.
- Metabase : filtres et drill-down.

À capturer : KPI compactes, tâches à faire, graphe CA, activité récente.

### Stock

- Shopify Products : table produits + bulk actions.
- AG Grid demo : densité table.
- Cardmarket : tables d’offres et états.
- TCGplayer : pricing et market price.
- Collectr : carte + valeur.

À capturer : table compacte, filtres, image carte en ligne, drawer détail.

### Lives Whatnot

- Whatnot : dynamique live.
- Shopify POS : actions tactiles.
- Square POS : caisse simple.
- SortableJS : ordre de lots.
- Linear cycles : préparation structurée.

À capturer : queue, lot actif, ventes récentes, actions rapides.

### Ventes Vinted

- Vinted : listing photo/statut.
- Shopify Orders : workflow commande.
- eBay Seller Hub : tâches vendeur.
- Stripe transaction details : timeline paiement.
- Cardmarket orders : vente spécialisée carte.

À capturer : tabs statut, table ventes, détail vente, timeline.

### Dépenses

- Ramp : dépense moderne.
- Brex : budgets/dépenses.
- Pennylane : comptabilité accessible.
- Revolut Business : transactions mobile.
- QuickBooks/Xero : catégories et rapports.

À capturer : table transactions, receipt drawer, catégories, période.

### Base cartes

- Pokécardex : séries et galerie.
- TCGplayer : fiche carte/prix.
- Cardmarket : offres par état.
- Collectr : portfolio mobile.
- PriceCharting : historique prix.

À capturer : galerie, fiche carte, prix, historique, ajout au stock.

### Mobile

- Revolut : bottom navigation, transactions.
- Shopify mobile : commandes/produits.
- Square POS : caisse tactile.
- Collectr : scan/portfolio carte.
- Vinted/Whatnot : marketplace mobile.

À capturer : bottom nav, action centrale, bottom sheet, liste compacte, détail carte.

## Mini-wireframes visuels à utiliser comme base de discussion

### Desktop — Stock dense avec drawer

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ Sidebar      │ Top bar: Search / Boutique / + Ajouter / Alertes / Profil   │
├──────────────┼──────────────────────────────────────────────────────────────┤
│ Dashboard    │ Stock                                                       │
│ Stock ●      │ [Toutes] [À vendre] [Réservées] [Vendues] [À vérifier]      │
│ Lives        │ Search…  Plateforme ▾  Série ▾  État ▾  Prix ▾   Export     │
│ Vinted       │ ┌────────────────────────────────────────────────────────┐  │
│ Dépenses     │ │ □ Img  Carte          Série   État Qté Achat Vente Marge│  │
│ Objectifs    │ │ □ ▣    Dracaufeu...   151     NM   1   42€   70€   28€ │  │
│ Rapports     │ │ □ ▣    Pikachu...     PAL     EX   3   4€    9€    5€  │  │
│ Base cartes  │ │ □ ▣    Mew...         MEW     NM   1   18€   30€   12€ │  │
│ Paramètres   │ └────────────────────────────────────────────────────────┘  │
│              │ Drawer détail: image / prix / historique / actions          │
└──────────────┴──────────────────────────────────────────────────────────────┘
```

### Desktop — Dashboard vendeur opérationnel

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│ Dashboard                                                                   │
│ Période: Ce mois ▾                                         + Ajouter vente  │
├───────────────┬───────────────┬───────────────┬───────────────┬────────────┤
│ CA            │ Marge estimée │ Ventes à faire│ Dépenses      │ Objectif   │
│ 2 840€ +12%   │ 910€ +8%      │ 14 à traiter  │ 420€          │ 71%        │
├───────────────────────────────────────────────┬─────────────────────────────┤
│ Courbe CA / marge par jour                     │ À traiter maintenant        │
│                                               │ - 8 colis Vinted             │
│                                               │ - 3 lots Whatnot à vérifier  │
│                                               │ - 2 dépenses sans reçu       │
├───────────────────────────────────────────────┴─────────────────────────────┤
│ Activité récente : ventes, stock, dépenses, alertes                         │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Mobile — App distincte

```text
┌─────────────────────────────┐
│ Bonjour — Boutique active   │
│ CA mois 2 840€   Marge 910€ │
├─────────────────────────────┤
│ À faire                     │
│ • 8 ventes à expédier       │
│ • 3 cartes à vérifier       │
│ • 2 dépenses sans reçu      │
├─────────────────────────────┤
│ Recherche carte ou vente…   │
├─────────────────────────────┤
│ Dernières ventes            │
│ ▣ Pikachu — Vinted — 12€    │
│ ▣ Mew — Whatnot — 30€       │
├─────────────────────────────┤
│ Accueil  Stock  +  Ventes Plus │
└─────────────────────────────┘
```

## Références visuelles à ne pas copier telles quelles

| Référence | Pourquoi ne pas copier |
| --- | --- |
| Linear | trop souvent copié, risque produit froid |
| Vercel | trop vide pour ERP opérationnel |
| Notion | trop document/workspace pour stock et finance |
| Cardmarket | très efficace mais esthétique datée |
| Amazon Seller Central | trop complexe et anxiogène |
| Dribbble dashboard shots | souvent beaux mais irréalistes et non testés en production |

## Décision visuelle mise à jour

La prochaine étape de refonte ne doit pas commencer par coder. Elle doit commencer par constituer un **Figma ou équivalent** avec :

1. 10 captures desktop denses ;
2. 10 captures stock/e-commerce ;
3. 10 captures finance/dépenses ;
4. 10 captures cartes/collection ;
5. 10 captures mobile ;
6. 5 wireframes Climax basés sur les captures retenues ;
7. 1 direction visuelle validée humainement.
