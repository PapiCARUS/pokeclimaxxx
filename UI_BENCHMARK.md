# UI Benchmark — ERP vendeur Whatnot/Vinted/cartes

Date de recherche : 2026-07-11.

## Méthode et limites

- Sources privilégiées : documentation officielle, design systems publics, changelogs, dépôts GitHub et pages produit.
- Les interfaces SaaS fermées ne sont pas toutes consultables sans compte ; l’analyse se concentre alors sur docs publiques, captures officielles, changelogs et patterns visibles.
- Fait = élément documenté par une source. Opinion = recommandation appliquée à notre ERP.

## Produits analysés

### Linear

- Référence : https://linear.app/changelog et dashboards https://linear.app/changelog/2025-07-24-dashboards
- Faits observables : Linear met en avant des dashboards modulaires, filtrables, avec charts, tables, métriques uniques et drill-down vers les éléments sous-jacents.
- Intéressant : densité élevée, navigation rapide, polish visuel, raccourcis, vues filtrées, dashboards personnalisables.
- Adapté à notre ERP : dashboard vendeur configurable, listes de tâches stock/ventes/lives, vues par statut, raccourcis clavier, commande rapide.
- Ne pas copier : esthétique trop “produit dev” et minimaliste pour des vendeurs non techniques ; éviter de masquer les actions métier derrière trop de raccourcis.
- Écrans à observer : dashboards, vues liste filtrées, triage, empty states, changelog.

### Stripe Dashboard

- Référence : https://docs.stripe.com/dashboard/basics
- Faits observables : le dashboard Stripe sert à gérer les ressources du compte, rechercher des transactions, inviter des membres, surveiller l’intégration et utiliser des raccourcis clavier.
- Intéressant : hiérarchie claire, recherche globale, pages ressources, détails latéraux, onboarding configuration, logs développeur.
- Adapté : ventes, dépenses, paiements futurs, settings organisation, historique d’activité, recherche globale.
- Ne pas copier : complexité financière et vocabulaire paiement avant d’avoir le module billing.
- Écrans à observer : transactions, customers, reports, settings, developer dashboard.

### Vercel

- Références : https://vercel.com/docs/projects et https://vercel.com/docs/deployments
- Faits observables : Vercel centralise projets, déploiements, logs, analytics, ressources et paramètres projet ; les pages détaillent statuts, environnements, URLs et observabilité.
- Intéressant : timeline d’événements, statuts visibles, navigation projet > section > détail, logs filtrables.
- Adapté : lives, imports, synchronisations, tâches de migration, statuts de vente, erreurs d’intégration.
- Ne pas copier : vocabulaire infra ; trop d’états techniques peut nuire aux vendeurs.
- Écrans à observer : liste projets, détail déploiement, logs, settings.

### GitHub / Primer

- Références : https://primer.style/ et https://primer.style/product/getting-started/
- Faits observables : Primer est le design system de GitHub, construit pour des expériences cohérentes, accessibles et responsive.
- Intéressant : navigation dense, tables de issues/PR, filtres sauvegardables, labels, états, activité, empty states.
- Adapté : inventaire filtré, ventes, cartes, alertes, historique d’activité.
- Ne pas copier : surcharge de métadonnées si l’utilisateur n’a pas besoin de chaque colonne.
- Écrans à observer : issues, projects, repository settings, notifications.

### Notion

- Références : https://www.notion.com/help/intro-to-databases, https://www.notion.com/help/guides/using-database-views et https://www.notion.com/help/galleries
- Faits observables : Notion propose plusieurs vues pour une même base : table, list, board, gallery, calendar, timeline.
- Intéressant : vues multiples, propriétés configurables, filtres, galerie visuelle.
- Adapté : base cartes en galerie/table, stock en table, objectifs en board, lives en calendrier.
- Ne pas copier : liberté excessive qui peut dégrader la cohérence ERP.
- Écrans à observer : database views, gallery view, properties panel.

### Odoo

- Références : https://www.odoo.com/documentation/19.0/applications/inventory_and_mrp/inventory.html et https://www.odoo.com/app/inventory
- Faits observables : Odoo Inventory couvre inventaire, warehouse management, lead times, replenishment, routes avancées et visibilité temps réel.
- Intéressant : workflows métier complets, opérations, inventaire physique, routes, replenishment.
- Adapté : stock, alertes, mouvements, inventaires, achats/reventes, dépenses.
- Ne pas copier : profondeur ERP trop lourde pour petits vendeurs au début.
- Écrans à observer : inventory dashboard, product moves, physical inventory, reporting.

### ERPNext

- Références : https://github.com/frappe/erpnext et https://frappe.io/erpnext
- Faits observables : ERPNext est un ERP open source actif, avec de nombreuses releases ; le dépôt GitHub indique une release récente en juillet 2026.
- Intéressant : modules métier intégrés, stock, ventes, achats, accounting, permissions.
- Adapté : structure de workflows, audit, rôles, rapports.
- Ne pas copier : densité fonctionnelle et architecture Frappe si l’objectif est de rester léger.
- Écrans à observer : stock ledger, item list, sales invoice, dashboard modules.

### Shopify Admin / Polaris

- Références : https://shopify.dev/docs/api/app-home/web-components et https://www.shopify.com/partners/blog/polaris-unified-and-for-the-web
- Faits observables : Polaris propose des composants cohérents pour l’admin Shopify, désormais orientés web components utilisables avec ou sans framework.
- Intéressant : patterns commerce, admin marchand, formulaires, tables, filtres, settings.
- Adapté : ERP vendeur, produits, commandes, paramètres boutique.
- Ne pas copier : trop d’alignement “app Shopify” si notre produit est autonome.
- Écrans à observer : product list, order list, settings, onboarding app.

### Square Dashboard

- Référence : https://squareup.com/us/en/point-of-sale/features/dashboard
- Intéressant : KPIs, ventes, paiements, catalogue, clients, équipe.
- Adapté : dashboard vendeur, suivi ventes/dépenses, rapports simples.
- Ne pas copier : focalisation POS physique si l’ERP est orienté marketplaces/live selling.
- Écrans à observer : sales reports, item library, customer list.

### Lightspeed

- Référence : https://www.lightspeedhq.com/pos/retail/
- Intéressant : retail inventory, POS, purchase orders, multi-location.
- Adapté : stock multi-boutique futur, catalogue, achats, marges.
- Ne pas copier : complexité POS retail complète.
- Écrans à observer : inventory, purchasing, reporting.

### Pennylane

- Référence : https://www.pennylane.com/fr
- Intéressant : approche finance claire, navigation par tâches, statuts de documents.
- Adapté : dépenses, rapports, marge, TVA/finance plus tard.
- Ne pas copier : posture comptable complète avant validation besoins vendeurs.
- Écrans à observer : dépenses, documents, dashboard financier.

### Revolut Business

- Référence : https://www.revolut.com/business/
- Intéressant : dashboard financier, cartes, comptes, transactions, mobile-first business.
- Adapté : dépenses, cashflow, alertes, version mobile rapide.
- Ne pas copier : identité bancaire premium trop éloignée du stock/cartes.
- Écrans à observer : transactions, analytics, mobile account overview.

### Références complémentaires utiles

- Airtable : vues grille/galerie/formulaire, champs configurables — https://www.airtable.com/product
- Retool : densité d’outils internes, tables/actions rapides — https://retool.com/
- Metabase : dashboards analytiques open source — https://www.metabase.com/
- Collectr : portfolio mobile TCG — https://play.google.com/store/apps/details?id=com.collectrinc.collectr

## Classement par composant

### Sidebar / navigation

- GitHub : navigation hiérarchique robuste pour sections nombreuses.
- Stripe : navigation produit + recherche globale.
- Shopify Admin : navigation commerce claire.
- Linear : navigation compacte et rapide.
- Recommandation : sidebar desktop persistante + recherche globale + favoris/vues sauvegardées.

### Dashboard KPI

- Linear : dashboards modulaires, filtres, drill-down.
- Stripe : métriques liées aux ressources et périodes.
- Square : KPIs ventes simples.
- Recommandation : widgets configurables mais presets par défaut : ventes, marge, stock faible, lives, dépenses, objectifs.

### Tableaux

- GitHub : tables denses avec labels, filtres, statuts.
- Shopify : listes produits/commandes marchandes.
- Odoo/ERPNext : listes métier très complètes.
- Recommandation : table dense desktop avec colonnes configurables, densité réglable, filtres sauvegardés.

### Filtres

- GitHub : filtres textuels puissants.
- Notion : filtres visuels par propriétés.
- Linear : vues filtrées et ciblées.
- Recommandation : commencer par filtres visuels, puis recherche avancée syntaxée plus tard.

### Formulaires

- Stripe : formulaires settings structurés.
- Shopify Polaris : formulaires commerce cohérents.
- Odoo : formulaires métier complets.
- Recommandation : formulaires en sections, validation inline, sauvegarde explicite, état dirty visible.

### Paramètres

- Stripe/Vercel/GitHub : settings par sections avec danger zone.
- Recommandation : paramètres Organisation, Boutique, Import/Export, Utilisateurs, Sécurité, Apparence.

### États vides

- Linear/Stripe/Shopify : empty states orientés action.
- Recommandation : message court + action primaire + exemple/import CSV/JSON.

### Mobile

- Revolut Business : consultation et actions rapides.
- Shopify : patterns marchands mobiles.
- Collectr : collection TCG mobile.
- Recommandation : version distincte, pas une table desktop compressée.

### Base cartes / galerie

- Notion Gallery : visualisation par cartes.
- Collectr/PokeTrax : collection et valeur.
- Recommandation : galerie avec image, état, quantité, prix, rareté, tags, bascule liste/table.

### Onboarding

- Stripe/Vercel/Shopify : checklist de configuration.
- Recommandation : onboarding progressif : importer stock, créer boutique, connecter marketplace plus tard, configurer objectifs.

### Facturation

- Stripe Billing : référence future, pas maintenant.
- Recommandation : documenter seulement l’espace futur ; ne pas construire le billing en bêta.
