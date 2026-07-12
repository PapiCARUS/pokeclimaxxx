# UI Research Master — Refonte ERP Climax

## Méthode et périmètre

Cette recherche prépare une direction UI/UX forte avant toute reprise du code. Elle compare des produits réels utilisés en ERP, SaaS B2B, finance, e-commerce, stock, CRM, analytics, marketplace, seller tools et collection/cartes.

Distinction utilisée :

- **Fait** : information directement observable sur le produit, sa documentation ou sa page officielle.
- **Observation** : lecture UI/UX à partir des écrans, patterns publics, démos, captures, documentations ou usages connus.
- **Recommandation** : application proposée pour ERP Climax.

## Synthèse des familles analysées

| Famille | Références fortes | Apport pour ERP Climax | Risque |
| --- | --- | --- | --- |
| B2B dense et sobre | Linear, GitHub, Retool, Supabase | efficacité, densité, lisibilité | peut sembler froid |
| Financier premium | Stripe, Ramp, Brex, Wise, Revolut Business | confiance, tableaux, détails transactionnels | trop fintech si mal dosé |
| E-commerce opérationnel | Shopify Admin, Square, Lightspeed, Shopify POS | flux vendeur, stock, commandes, actions rapides | trop retail généraliste |
| ERP/CRM mature | Odoo, ERPNext, HubSpot, Salesforce | profondeur fonctionnelle, navigation métier | complexité excessive |
| Analytics/reporting | Metabase, Looker Studio, Tableau, Power BI | dashboards, filtres, drill-down | dashboards trop abstraits |
| Marketplace/seller tools | Whatnot, Vinted, Cardmarket, TCGplayer | contexte cible, vente, cartes | UI consommateur moins adaptée B2B |
| Collection/cartes | Collectr, PriceCharting, Pokécardex, Ludex | galerie, valeur portfolio, scan, pricing | mobile-first et moins ERP |

## Corpus de références principales

### 1. Linear

- URL : https://linear.app/
- Catégorie : productivité / issue tracking.
- Type : SaaS B2B mature.
- Qualité perçue : très élevée.
- Densité : moyenne à élevée, très maîtrisée.
- Style visuel : sombre/clair, minimal, précis, très peu décoratif.
- Faits : Linear met en avant la vitesse, la priorisation, les cycles et une interface centrée sur les workflows produit.
- Observations : la sidebar est compacte, les listes sont denses, la hiérarchie typographique est fine, les actions secondaires restent discrètes.
- Points forts : navigation rapide, raccourcis, command palette, détails en panneau, statut clair.
- Points faibles : style très copié, risque de paraître froid.
- Composants intéressants : sidebar, listes, détails latéraux, filtres, command menu.
- Compatibilité Climax : forte pour dashboard, stock, objectifs et rapports.
- À reprendre : densité contrôlée, sobriété, vitesse perçue, panneau détail.
- À éviter : copier l’esthétique sombre violette/noire sans identité propre.

### 2. Stripe Dashboard

- URL : https://dashboard.stripe.com/ et https://stripe.com/
- Catégorie : finance / paiements.
- Type : dashboard financier B2B.
- Qualité perçue : très élevée.
- Densité : élevée mais lisible.
- Style visuel : premium, net, typographie propre, cards fonctionnelles.
- Faits : Stripe structure fortement paiements, clients, reporting, événements et documentation.
- Observations : les tableaux sont excellents pour données financières, avec statuts, montants, dates, détails transactionnels.
- Points forts : confiance, états, recherche, filtres, détails de transaction.
- Points faibles : peut être trop financier pour un ERP vendeur si appliqué partout.
- Composants intéressants : tableaux, filtres, KPI, timelines, détails paiement.
- Compatibilité Climax : très forte pour dépenses, rapports, ventes et objectifs.
- À reprendre : rigueur des montants, détails événementiels, statuts sobres.
- À éviter : surcharge de micro-informations non utiles aux vendeurs.

### 3. GitHub

- URL : https://github.com/
- Catégorie : productivité / collaboration / développeurs.
- Type : plateforme B2B/B2C.
- Qualité perçue : élevée.
- Densité : élevée.
- Style visuel : utilitaire, mature, peu décoratif.
- Faits : GitHub gère listes, filtres, recherches, onglets, activités, permissions, états.
- Observations : excellent exemple de navigation secondaire, tableaux/listes scannables et états vides sobres.
- Points forts : information dense, navigation stable, filtres mémorisables.
- Points faibles : parfois très textuel et intimidant.
- Composants intéressants : onglets, breadcrumbs, listes, états, labels.
- Compatibilité Climax : forte pour base cartes, stock, paramètres.
- À reprendre : labels, structure listes+détails, densité lisible.
- À éviter : jargon ou complexité de filtres avancés exposée trop tôt.

### 4. Vercel

- URL : https://vercel.com/dashboard
- Catégorie : cloud / SaaS développeur.
- Type : dashboard B2B.
- Qualité perçue : élevée.
- Densité : moyenne.
- Style visuel : minimal premium, noir/blanc, cards nettes.
- Points forts : hiérarchie claire, pages projet, navigation simple.
- Points faibles : blanc important, moins adapté à opérations stock volumineuses.
- Composants intéressants : cards projet, settings, breadcrumbs, top bar.
- Compatibilité Climax : moyenne pour paramètres et dashboard, faible pour tables denses.
- À reprendre : settings propres, navigation concise.
- À éviter : trop d’espace vide façon marketing SaaS.

### 5. Notion

- URL : https://www.notion.com/
- Catégorie : productivité / workspace.
- Type : SaaS collaboratif.
- Qualité perçue : élevée.
- Densité : variable.
- Style visuel : blanc, modulaire, souple.
- Points forts : blocs, bases de données, vues multiples.
- Points faibles : manque de rigueur opérationnelle pour ERP critique.
- Composants intéressants : pages, tables, vues, side peek, templates.
- Compatibilité Climax : moyenne pour base cartes et notes, faible pour finance stricte.
- À reprendre : flexibilité des vues stock.
- À éviter : interface trop document, trop blanche et molle.

### 6. Shopify Admin

- URL : https://www.shopify.com/admin
- Catégorie : e-commerce.
- Type : outil vendeur / admin marchand.
- Qualité perçue : très élevée.
- Densité : moyenne à élevée.
- Style visuel : opérationnel, clair, mature.
- Points forts : produits, commandes, clients, analytics, actions contextuelles.
- Points faibles : très orienté boutique en ligne classique.
- Composants intéressants : sidebar, tables produits, bulk actions, filtres, vues enregistrées.
- Compatibilité Climax : très forte pour stock, ventes Vinted, lives Whatnot.
- À reprendre : logique produits/commandes, filtres sauvegardés, actions groupées.
- À éviter : copier les concepts e-commerce qui ne correspondent pas aux lives.

### 7. Odoo

- URL : https://www.odoo.com/
- Catégorie : ERP.
- Type : suite ERP/CRM.
- Qualité perçue : élevée mais très large.
- Densité : élevée.
- Style visuel : ERP moderne, modulaire.
- Points forts : couverture métier, vues kanban/liste/formulaire, modules.
- Points faibles : complexité, surcharge possible.
- Composants intéressants : apps/modules, formulaires, vues liste, kanban, reporting.
- Compatibilité Climax : forte pour architecture ERP, modérée visuellement.
- À reprendre : alternance liste/kanban/formulaire.
- À éviter : navigation trop module-factory sans personnalité.

### 8. ERPNext

- URL : https://erpnext.com/ et https://github.com/frappe/erpnext
- Catégorie : ERP open source.
- Type : ERP complet.
- Qualité perçue : mature.
- Densité : élevée.
- Style visuel : utilitaire.
- Points forts : stock, ventes, achats, comptabilité, formulaires profonds.
- Points faibles : UI moins distinctive.
- Composants intéressants : bureau modulaire, doctypes, listes, détails.
- Compatibilité Climax : forte pour modèle métier et stock.
- À reprendre : rigueur des entités et états.
- À éviter : apparence trop générique d’ERP open source.

### 9. Pennylane

- URL : https://www.pennylane.com/
- Catégorie : finance / comptabilité.
- Type : SaaS B2B financier.
- Qualité perçue : élevée.
- Densité : moyenne.
- Style visuel : professionnel, français, financier accessible.
- Points forts : dépenses, factures, trésorerie, accompagnement.
- Points faibles : moins stock/vente live.
- Composants intéressants : dashboards financiers, listes de transactions, statuts.
- Compatibilité Climax : forte pour dépenses et rapports.
- À reprendre : ton financier accessible aux petits vendeurs.
- À éviter : vocabulaire comptable trop lourd.

### 10. Revolut Business

- URL : https://www.revolut.com/business/
- Catégorie : finance / banque.
- Type : app business web/mobile.
- Qualité perçue : élevée.
- Densité : moyenne.
- Style visuel : premium, contrasté, mobile-first.
- Points forts : cartes, transactions, comptes, actions rapides.
- Points faibles : style très fintech.
- Composants intéressants : transactions, cartes, KPI, alertes.
- Compatibilité Climax : forte pour dépenses, mobile, soldes.
- À reprendre : lisibilité mobile et actions rapides.
- À éviter : animations ou gradients trop marketing.

### 11. Square

- URL : https://squareup.com/
- Catégorie : POS / commerce.
- Type : outil vendeur.
- Qualité perçue : élevée.
- Densité : moyenne.
- Style visuel : clair, pratique, commerce local.
- Points forts : POS, articles, ventes, clients, analytics.
- Points faibles : moins spécialisé collection/cartes.
- Composants intéressants : caisse, catalogue, reporting, mobile.
- Compatibilité Climax : forte pour vendeur petit commerce.
- À reprendre : pragmatisme et clarté opérationnelle.
- À éviter : simplification excessive du stock cartes.

### 12. Lightspeed

- URL : https://www.lightspeedhq.com/
- Catégorie : POS / retail.
- Type : commerce, stock, caisse.
- Qualité perçue : élevée.
- Densité : moyenne à élevée.
- Style visuel : retail professionnel.
- Points forts : inventaire, ventes, clients, POS.
- Points faibles : interface parfois lourde selon modules.
- Composants intéressants : inventaire, variations, rapports.
- Compatibilité Climax : très forte pour stock et ventes.
- À reprendre : gestion inventaire+vente.
- À éviter : complexité retail multi-site prématurée.

### 13. HubSpot

- URL : https://www.hubspot.com/
- Catégorie : CRM.
- Type : SaaS B2B mature.
- Qualité perçue : élevée.
- Densité : élevée.
- Style visuel : CRM riche, coloré mais structuré.
- Points forts : pipelines, fiches contact, activités, filtres.
- Points faibles : lourdeur CRM et upsell.
- Composants intéressants : tables CRM, fiche détail, timeline activité.
- Compatibilité Climax : forte pour clients/acheteurs et ventes.
- À reprendre : fiche détail avec timeline.
- À éviter : surcharge marketing et trop de modules.

### 14. Salesforce

- URL : https://www.salesforce.com/
- Catégorie : CRM / enterprise.
- Type : plateforme B2B.
- Qualité perçue : mature.
- Densité : très élevée.
- Style visuel : enterprise configurable.
- Points forts : personnalisation, dashboards, permissions, pipelines.
- Points faibles : complexité massive.
- Composants intéressants : fiches objets, rapports, listes, actions.
- Compatibilité Climax : moyenne, surtout pour fiches et permissions futures.
- À reprendre : robustesse des fiches objet.
- À éviter : lourdeur enterprise.

### 15. Monday.com

- URL : https://monday.com/
- Catégorie : productivité / opérations.
- Type : SaaS collaboratif.
- Qualité perçue : élevée.
- Densité : élevée et colorée.
- Style visuel : boards colorés, cells, automation.
- Points forts : vues, statuts, collaboration.
- Points faibles : trop coloré pour ERP financier.
- Composants intéressants : board, statuts, filtres, vues.
- Compatibilité Climax : moyenne pour objectifs et lives.
- À reprendre : statuts visibles, vues configurables.
- À éviter : arc-en-ciel de tags.

### 16. Asana

- URL : https://asana.com/
- Catégorie : productivité.
- Type : gestion de travail.
- Qualité perçue : élevée.
- Densité : moyenne.
- Style visuel : clair, organisé, accessible.
- Points forts : listes, calendrier, objectifs, timeline.
- Points faibles : pas assez orienté données métier.
- Composants intéressants : objectifs, tâches, milestones.
- Compatibilité Climax : forte pour Objectifs.
- À reprendre : suivi objectifs/action items.
- À éviter : approche projet trop générique.

### 17. Airtable

- URL : https://www.airtable.com/
- Catégorie : data/productivité.
- Type : base de données collaborative.
- Qualité perçue : élevée.
- Densité : élevée.
- Style visuel : tableur moderne.
- Points forts : vues table/kanban/gallery/form, filtres.
- Points faibles : peut ressembler à outil générique.
- Composants intéressants : data grid, vues, gallery.
- Compatibilité Climax : très forte pour stock et base cartes.
- À reprendre : vues multiples et galerie cartes.
- À éviter : laisser l’utilisateur construire lui-même l’ERP.

### 18. Metabase

- URL : https://www.metabase.com/
- Catégorie : analytics.
- Type : BI/dashboard.
- Qualité perçue : élevée.
- Densité : moyenne à élevée.
- Style visuel : analytique, clair.
- Points forts : dashboards, filtres, questions, drill-down.
- Points faibles : interface analytique pas toujours opérationnelle.
- Composants intéressants : dashboards, graphiques, filtres globaux.
- Compatibilité Climax : très forte pour Rapports.
- À reprendre : filtres globaux et cards analytiques.
- À éviter : transformer toute l’app en BI.

### 19. Retool

- URL : https://retool.com/
- Catégorie : internal tools.
- Type : builder B2B.
- Qualité perçue : élevée.
- Densité : très élevée.
- Style visuel : opérationnel, data-heavy.
- Points forts : tables, forms, drawers, actions, panels.
- Points faibles : peut sembler interne/admin brut.
- Composants intéressants : data grids, forms, drawers, workflows.
- Compatibilité Climax : très forte pour ERP dense.
- À reprendre : densité et efficacité des workflows.
- À éviter : aspect trop outil interne sans polish.

### 20. Supabase

- URL : https://supabase.com/dashboard
- Catégorie : cloud/data.
- Type : dashboard développeur.
- Qualité perçue : élevée.
- Densité : élevée.
- Style visuel : sombre/clair, technique, tables.
- Points forts : table editor, logs, settings, navigation.
- Points faibles : trop développeur.
- Composants intéressants : table editor, side nav, logs.
- Compatibilité Climax : moyenne pour settings et tables.
- À reprendre : table editor clair.
- À éviter : jargon technique.

### 21. Plaid

- URL : https://plaid.com/
- Catégorie : finance/API.
- Type : infrastructure financière.
- Qualité perçue : élevée.
- Densité : moyenne.
- Style visuel : fiable, fintech.
- Points forts : statuts, connexions, flux finance.
- Points faibles : très API/infrastructure.
- Composants intéressants : onboarding, status, docs UI.
- Compatibilité Climax : faible à moyenne, surtout finance future.
- À reprendre : pédagogie et confiance.
- À éviter : abstractions API.

### 22. Ramp

- URL : https://ramp.com/
- Catégorie : finance / dépenses.
- Type : gestion dépenses B2B.
- Qualité perçue : très élevée.
- Densité : élevée.
- Style visuel : premium, finance opérationnelle.
- Points forts : dépenses, reçus, contrôles, tableaux.
- Points faibles : très corporate.
- Composants intéressants : expense tables, approvals, policies.
- Compatibilité Climax : forte pour Dépenses.
- À reprendre : statut des dépenses et pièces justificatives.
- À éviter : complexité d’approbation enterprise.

### 23. Brex

- URL : https://www.brex.com/
- Catégorie : finance / spend management.
- Type : SaaS financier.
- Qualité perçue : très élevée.
- Densité : élevée.
- Style visuel : premium enterprise.
- Points forts : dépenses, cartes, budgets, reporting.
- Points faibles : trop corporate.
- Composants intéressants : budgets, tables transactionnelles, alertes.
- Compatibilité Climax : forte pour Objectifs/Dépenses.
- À reprendre : budget vs réalisé.
- À éviter : ton grand compte.

### 24. Wise Business

- URL : https://wise.com/business/
- Catégorie : finance internationale.
- Type : compte business.
- Qualité perçue : élevée.
- Densité : moyenne.
- Style visuel : clair, accessible.
- Points forts : transactions, soldes, conversion, mobile.
- Points faibles : usage finance limité.
- Composants intéressants : compte, activité, frais.
- Compatibilité Climax : moyenne pour finance et mobile.
- À reprendre : clarté des coûts et soldes.
- À éviter : simplification excessive.

### 25. Shopify POS

- URL : https://www.shopify.com/pos
- Catégorie : POS.
- Type : app caisse.
- Qualité perçue : élevée.
- Densité : mobile/tablette moyenne.
- Style visuel : tactile, opérationnel.
- Points forts : actions rapides, catalogue, ventes physiques.
- Points faibles : moins desktop analytique.
- Composants intéressants : grille produits, panier, actions rapides.
- Compatibilité Climax : forte pour live selling et mobile.
- À reprendre : vitesse de vente, grandes zones tactiles.
- À éviter : UI uniquement caisse.

### 26. Whatnot

- URL : https://www.whatnot.com/
- Catégorie : marketplace live shopping.
- Type : marketplace vendeur/acheteur.
- Qualité perçue : élevée côté consommateur.
- Densité : élevée pendant live.
- Style visuel : social commerce, vidéo, enchères.
- Points forts : live, enchères, flux, urgence.
- Points faibles : moins ERP, interface très événementielle.
- Composants intéressants : live queue, lots, statuts, ventes rapides.
- Compatibilité Climax : critique pour module Lives Whatnot.
- À reprendre : temporalité live, lots, statut de vente.
- À éviter : chaos visuel du live dans les pages de gestion.

### 27. Vinted

- URL : https://www.vinted.com/
- Catégorie : marketplace C2C.
- Type : vente seconde main.
- Qualité perçue : élevée grand public.
- Densité : moyenne.
- Style visuel : marketplace claire.
- Points forts : annonces, photos, prix, statuts, messages.
- Points faibles : pas outil vendeur pro complet.
- Composants intéressants : listing cards, filtres, statuts vente.
- Compatibilité Climax : critique pour Ventes Vinted.
- À reprendre : statut annonce/vente et galerie produit.
- À éviter : trop d’éléments sociaux.

### 28. Cardmarket

- URL : https://www.cardmarket.com/
- Catégorie : marketplace cartes.
- Type : vente cartes TCG.
- Qualité perçue : fonctionnelle, très spécialisée.
- Densité : élevée.
- Style visuel : utilitaire, ancien mais efficace.
- Points forts : recherche carte, prix, état, offres, vendeurs.
- Points faibles : UI datée.
- Composants intéressants : tables d’offres, pricing, état carte.
- Compatibilité Climax : très forte pour base cartes et pricing.
- À reprendre : densité des offres et états.
- À éviter : esthétique datée.

### 29. Pokécardex

- URL : https://www.pokecardex.com/
- Catégorie : base cartes Pokémon.
- Type : catalogue / collection.
- Qualité perçue : spécialisée.
- Densité : moyenne à élevée.
- Style visuel : communautaire, catalogue.
- Points forts : séries, cartes, visuels, checklist.
- Points faibles : moins outil pro vendeur.
- Composants intéressants : galerie cartes, filtres séries, checklist.
- Compatibilité Climax : très forte pour Base cartes.
- À reprendre : navigation par série et visuels cartes.
- À éviter : interface trop fan-site.

### 30. Collectr

- URL : https://getcollectr.com/
- Catégorie : collection / portfolio TCG.
- Type : app mobile collection.
- Qualité perçue : élevée.
- Densité : mobile moyenne.
- Style visuel : portfolio financier appliqué aux cartes.
- Points forts : valeur collection, scan, portfolio, trade analyzer.
- Points faibles : pricing à vérifier selon sources, moins ERP.
- Composants intéressants : portfolio, valeur, scan, card details.
- Compatibilité Climax : forte pour mobile et base cartes.
- À reprendre : valeur portefeuille et fiche carte.
- À éviter : faire croire à une précision financière parfaite.

### 31. TCGplayer

- URL : https://www.tcgplayer.com/
- Catégorie : marketplace TCG.
- Type : marketplace + outils prix.
- Qualité perçue : élevée.
- Densité : élevée.
- Style visuel : commerce spécialisé.
- Points forts : prix de marché, offres, vendeurs, catalogue.
- Points faibles : navigation dense.
- Composants intéressants : market price, listing, état, seller tools.
- Compatibilité Climax : très forte pour cartes et pricing.
- À reprendre : prix marché et états cartes.
- À éviter : surcharge marketplace.

### 32. PriceCharting

- URL : https://www.pricecharting.com/
- Catégorie : pricing collection.
- Type : base prix jeux/cartes.
- Qualité perçue : utile, utilitaire.
- Densité : élevée.
- Style visuel : fonctionnel, peu premium.
- Points forts : historique prix, recherche, collection value.
- Points faibles : interface ancienne.
- Composants intéressants : price history, collection tracker.
- Compatibilité Climax : forte pour estimation valeur.
- À reprendre : historique prix lisible.
- À éviter : look daté.

### 33. QuickBooks

- URL : https://quickbooks.intuit.com/
- Catégorie : comptabilité.
- Type : finance PME.
- Qualité perçue : mature.
- Densité : moyenne à élevée.
- Style visuel : business accessible.
- Points forts : dépenses, factures, rapports, taxes.
- Points faibles : comptabilité lourde.
- Compatibilité Climax : forte pour dépenses/rapports, à simplifier.

### 34. Xero

- URL : https://www.xero.com/
- Catégorie : comptabilité.
- Type : SaaS PME.
- Qualité perçue : mature.
- Densité : moyenne.
- Style visuel : clair, finance PME.
- Points forts : dashboard financier, factures, réconciliation.
- Points faibles : pas vendeur cartes.
- Compatibilité Climax : moyenne pour dépenses/rapports.

### 35. Zoho Inventory

- URL : https://www.zoho.com/inventory/
- Catégorie : stock.
- Type : inventory management.
- Qualité perçue : mature.
- Densité : élevée.
- Style visuel : SaaS business classique.
- Points forts : articles, commandes, entrepôts, rapports.
- Points faibles : visuel générique.
- Compatibilité Climax : très forte pour stock.

### 36. Cin7

- URL : https://www.cin7.com/
- Catégorie : stock / retail operations.
- Type : inventory management.
- Qualité perçue : mature.
- Densité : élevée.
- Points forts : inventaire multicanal, commandes, intégrations.
- Points faibles : complexité.
- Compatibilité Climax : forte pour futur multicanal.

### 37. Katana

- URL : https://katanamrp.com/
- Catégorie : inventory / MRP.
- Type : stock production.
- Qualité perçue : élevée.
- Densité : élevée.
- Points forts : planning stock, production, commandes.
- Points faibles : production moins pertinente.
- Compatibilité Climax : moyenne, utile pour flux stock.

### 38. Sortly

- URL : https://www.sortly.com/
- Catégorie : stock mobile.
- Type : inventory app.
- Qualité perçue : élevée.
- Densité : mobile moyenne.
- Points forts : photos, QR, localisation, mobile.
- Points faibles : moins finance/ERP.
- Compatibilité Climax : forte pour stock mobile.

### 39. Fishbowl Inventory

- URL : https://www.fishbowlinventory.com/
- Catégorie : stock.
- Type : inventory management.
- Qualité perçue : mature.
- Densité : élevée.
- Points forts : inventaire, commandes, manufacturing.
- Points faibles : esthétique enterprise.
- Compatibilité Climax : moyenne.

### 40. Zoho CRM

- URL : https://www.zoho.com/crm/
- Catégorie : CRM.
- Type : CRM B2B.
- Qualité perçue : mature.
- Densité : élevée.
- Points forts : fiches, pipelines, automation.
- Points faibles : UI générique.
- Compatibilité Climax : moyenne pour clients/acheteurs.

### 41. Pipedrive

- URL : https://www.pipedrive.com/
- Catégorie : CRM.
- Type : pipeline ventes.
- Qualité perçue : élevée.
- Densité : moyenne.
- Points forts : pipeline simple, activités, priorités.
- Points faibles : pas stock.
- Compatibilité Climax : moyenne pour suivi ventes.

### 42. Intercom

- URL : https://www.intercom.com/
- Catégorie : support/CRM.
- Type : customer communication.
- Qualité perçue : élevée.
- Densité : élevée.
- Points forts : inbox, timeline, sidebar details.
- Points faibles : support-centric.
- Compatibilité Climax : moyenne pour acheteurs/messages.

### 43. Mixpanel

- URL : https://mixpanel.com/
- Catégorie : analytics produit.
- Type : BI comportementale.
- Qualité perçue : élevée.
- Densité : élevée.
- Points forts : funnels, cohorts, segments.
- Points faibles : pas ERP.
- Compatibilité Climax : moyenne pour rapports avancés.

### 44. Amplitude

- URL : https://amplitude.com/
- Catégorie : analytics produit.
- Type : dashboard analytics.
- Qualité perçue : élevée.
- Points forts : exploration, cohorts, charts.
- Points faibles : complexité analytique.
- Compatibilité Climax : faible à moyenne.

### 45. Datadog

- URL : https://www.datadoghq.com/
- Catégorie : monitoring.
- Type : dashboards techniques.
- Qualité perçue : très élevée.
- Densité : très élevée.
- Points forts : alertes, timelines, dashboards denses.
- Points faibles : trop technique.
- Compatibilité Climax : utile pour densité rapports/alertes.

### 46. Looker Studio

- URL : https://lookerstudio.google.com/
- Catégorie : BI.
- Type : dashboards/reporting.
- Qualité perçue : mature.
- Densité : variable.
- Points forts : filtres, graphiques, reporting partagé.
- Points faibles : dashboards parfois génériques.
- Compatibilité Climax : forte pour Rapports.

### 47. Tableau

- URL : https://www.tableau.com/
- Catégorie : BI.
- Type : analytics enterprise.
- Qualité perçue : mature.
- Densité : élevée.
- Points forts : visualisations avancées, drill-down.
- Points faibles : trop lourd pour bêta.
- Compatibilité Climax : inspiration seulement.

### 48. Microsoft Power BI

- URL : https://powerbi.microsoft.com/
- Catégorie : BI.
- Type : analytics enterprise.
- Qualité perçue : mature.
- Densité : élevée.
- Points forts : dashboards, rapports, filtres.
- Points faibles : look enterprise Microsoft.
- Compatibilité Climax : inspiration rapports.

### 49. Faire

- URL : https://www.faire.com/
- Catégorie : marketplace wholesale.
- Type : marketplace vendeur/retail.
- Qualité perçue : élevée.
- Densité : moyenne.
- Points forts : catalogue, commandes, marketplace B2B.
- Points faibles : pas cartes.
- Compatibilité Climax : moyenne pour vendeur marketplace.

### 50. eBay Seller Hub

- URL : https://www.ebay.com/sh/overview
- Catégorie : seller tools / marketplace.
- Type : dashboard vendeur.
- Qualité perçue : mature.
- Densité : élevée.
- Points forts : annonces, ventes, trafic, tâches.
- Points faibles : UI parfois lourde.
- Compatibilité Climax : très forte pour vendeur multicanal.

### 51. Amazon Seller Central

- URL : https://sellercentral.amazon.com/
- Catégorie : seller tools / marketplace.
- Type : dashboard vendeur.
- Qualité perçue : mature.
- Densité : très élevée.
- Points forts : inventaire, commandes, performance.
- Points faibles : complexité et anxiété utilisateur.
- Compatibilité Climax : forte pour structure, faible pour ton visuel.

### 52. Stocky by Shopify

- URL : https://apps.shopify.com/stocky
- Catégorie : inventory.
- Type : app stock Shopify.
- Qualité perçue : spécialisée.
- Densité : élevée.
- Points forts : inventaire, achats, prévisions.
- Points faibles : dépendant Shopify POS.
- Compatibilité Climax : forte pour stock.

## Contradictions observées entre références

1. **Densité vs respiration** : Retool, Stripe et Amazon Seller Central favorisent une forte densité ; Vercel et Notion favorisent une respiration plus large. Pour Climax, la densité doit être élevée dans Stock/Ventes/Rapports, mais plus respirée dans Dashboard/Objectifs.
2. **Esthétique premium vs utilitaire** : Stripe/Ramp/Brex sont premium ; Cardmarket/PriceCharting sont utilitaires mais très efficaces. Climax doit prendre la rigueur et non la froideur fintech.
3. **Mobile app vs desktop réduit** : Revolut, Collectr et Shopify POS montrent que le mobile doit être repensé autour d’actions rapides ; les ERP classiques tendent à réduire le desktop, ce qui serait à éviter.
4. **Personnalisation vs opinion forte** : Airtable/Notion donnent la main à l’utilisateur ; Shopify/Stripe proposent des flux opinionated. Climax doit être opinionated pour petits vendeurs, avec quelques vues sauvegardées plutôt qu’un builder générique.

## Recommandations principales

- Construire Climax comme un **outil vendeur opérationnel**, pas comme un dashboard marketing.
- Assumer une densité professionnelle avec des tableaux lisibles, actions groupées, panneaux détail et filtres sauvegardés.
- Donner une identité visuelle inspirée commerce/finance/cartes : sérieuse, compacte, précise, mais avec des touches collection.
- Éviter les grands blocs vides, les cartes KPI décoratives et les gradients IA.
- Faire du mobile une app séparée centrée sur consultation rapide, scan, stock, ventes, alertes et actions fréquentes.

## Addendum — Références visuelles

La recherche textuelle doit être complétée par un moodboard visuel. Le document `UI_VISUAL_REFERENCE_BOARD.md` liste des pages produit, galeries, démos et dépôts à ouvrir pour observer concrètement les écrans, captures, composants, densités et layouts avant de coder.

Décision mise à jour : aucune refonte UI ne devrait démarrer avant validation d’un board visuel de captures réelles et de wireframes Climax dérivés de ces références.
