# ERP Page Benchmarks — ERP Climax

## Dashboard

- Références : Stripe Dashboard, Shopify Analytics, Square Dashboard, Ramp, Pennylane, Revolut Business, Metabase, Databox, Linear, GitHub home.
- Structure observée : KPI prioritaires en haut, actions à traiter, activité récente, graphiques courts.
- Organisation : période active, comparaison précédente, alertes opérationnelles, liens drill-down.
- Composants : KPI cards, mini charts, liste d’activité, alertes, tâches.
- Densité : moyenne, plus éditoriale que les pages tables.
- Hiérarchie : 3 questions max : argent gagné, choses à faire, risques.
- Interactions : changement période, clic KPI, dismiss alerte.
- Erreurs fréquentes : dashboard vitrine, cards sans action, trop de vide, métriques vanity.
- Recommandations Climax : afficher CA/marge, ventes à traiter, stock à risque, dépenses du mois, objectif mensuel, prochain live.
- Layout possible : 4 KPI compactes, colonne `À faire`, graphique CA, feed activité.
- À conserver : vue synthétique.
- À supprimer : cartes décoratives.
- À repenser : prioriser tâches vendeur plutôt que métriques génériques.

## Stock

- Références : Shopify Products, Zoho Inventory, Lightspeed, Sortly, Airtable, Retool, ERPNext, Cardmarket, TCGplayer, Pokécardex, Collectr, Stocky.
- Structure observée : table dense, filtres, recherche, bulk actions, galerie optionnelle.
- Organisation : statut, plateforme, catégorie, série, prix achat, prix vente, quantité, localisation.
- Composants : data grid, filtres, drawer détail, galerie, import/export.
- Densité : élevée.
- Hiérarchie : table d’abord, KPI secondaire.
- Interactions : tri, filtre, sélection multiple, édition rapide, ouverture détail.
- Erreurs fréquentes : trop de cards produit, absence de bulk actions, images trop grandes, tables non alignées.
- Recommandations Climax : table compacte par défaut + galerie cartes pour Base cartes/stock visuel.
- Layout possible : toolbar filtres, table 70%, drawer détail 30%.
- À conserver : rapidité de consultation.
- À supprimer : grands blocs vides.
- À repenser : statut stock comme workflow vendeur.

## Lives Whatnot

- Références : Whatnot, Shopify POS, Square POS, Linear cycles, Airtable kanban, Trello, HubSpot pipeline, eBay Seller Hub, TCGplayer seller tools.
- Structure observée : préparation, file de lots, live, ventes, post-live.
- Organisation : lots planifiés, lots vendus, paiements/expéditions, anomalies.
- Composants : kanban, queue, table ventes, timer, statut, actions rapides.
- Densité : élevée pendant préparation, très focalisée pendant live.
- Hiérarchie : prochain lot, lot actif, actions immédiates.
- Interactions : marquer vendu, associer carte, modifier prix, noter acheteur.
- Erreurs fréquentes : page trop analytique pendant live, actions trop petites.
- Recommandations Climax : séparer préparation desktop et mode live simplifié.
- Layout possible : colonne lots, panneau lot actif, liste ventes récentes.
- À conserver : temporalité live.
- À supprimer : dashboard général dans l’écran live.
- À repenser : mode focus.

## Ventes Vinted

- Références : Vinted, Shopify Orders, eBay Seller Hub, Square, Lightspeed, HubSpot deals, Stripe payments, Cardmarket orders.
- Structure observée : liste ventes, statuts, client, montant, date, expédition.
- Organisation : en attente, payée, à expédier, expédiée, litige, archivée.
- Composants : table, cards marketplace, timeline vente, actions statut.
- Densité : moyenne à élevée.
- Hiérarchie : statut et prochaine action d’abord.
- Interactions : filtrer statut, marquer expédié, ajouter tracking, ouvrir détail.
- Erreurs fréquentes : mélanger annonces, ventes et messages.
- Recommandations Climax : page opérationnelle `Ventes à traiter` avant historique.
- Layout possible : tabs statut + table + drawer détail.
- À conserver : images produits.
- À supprimer : métriques non actionnables.
- À repenser : workflow expédition.

## Dépenses

- Références : Ramp, Brex, Pennylane, QuickBooks, Xero, Revolut Business, Wise Business, Stripe, Shopify finance reports.
- Structure observée : table transactions, catégories, justificatifs, statuts.
- Organisation : période, catégorie, moyen de paiement, projet/boutique, justificatif.
- Composants : table, KPI dépenses, upload reçu, filtres, export.
- Densité : élevée.
- Hiérarchie : montant, date, catégorie, statut justificatif.
- Interactions : catégoriser, joindre reçu, filtrer période.
- Erreurs fréquentes : formulaires comptables trop lourds.
- Recommandations Climax : dépenses vendeur simple : achat stock, frais port, matériel, plateforme, autres.
- Layout possible : KPI mensuel + table + drawer reçu.
- À conserver : rigueur financière.
- À supprimer : jargon comptable avancé.
- À repenser : capture rapide mobile.

## Objectifs

- Références : Asana Goals, Linear cycles, Monday goals, Ramp budgets, Brex budgets, Shopify analytics, Databox goals, Pipedrive targets.
- Structure observée : objectif, progression, échéance, actions liées.
- Organisation : mensuel, hebdo, plateforme, stock, marge.
- Composants : progress bars, KPI targets, timeline, checklist.
- Densité : moyenne.
- Hiérarchie : objectif principal + progression + écart.
- Interactions : modifier cible, lier KPI, marquer jalon.
- Erreurs fréquentes : objectifs abstraits non connectés aux données.
- Recommandations Climax : objectifs `CA`, `marge`, `stock écoulé`, `ventes live`, `dépenses max`.
- Layout possible : cards objectifs + graphique trajectoire.
- À conserver : motivation.
- À supprimer : gamification gratuite.
- À repenser : objectifs comme pilotage métier.

## Rapports

- Références : Metabase, Stripe, Shopify Analytics, Looker Studio, Tableau, Power BI, Ramp reporting, Pennylane, Databox, Mixpanel.
- Structure observée : filtres globaux, graphiques, tables détail, exports.
- Organisation : période, plateforme, catégorie, vente, stock, dépenses.
- Composants : charts, KPI, table détail, export, saved views.
- Densité : élevée.
- Hiérarchie : résumé puis analyse segmentée.
- Interactions : drill-down, filtres, export, comparaison période.
- Erreurs fréquentes : trop de charts, absence de décision.
- Recommandations Climax : rapports utiles aux petits vendeurs : marge réelle, stock dormant, plateformes rentables, dépenses.
- Layout possible : filtres sticky + 3 charts + table transactions.
- À conserver : export futur.
- À supprimer : visualisations décoratives.
- À repenser : récit analytique.

## Paramètres

- Références : Stripe settings, GitHub settings, Vercel settings, Shopify settings, Supabase settings, Notion settings, Linear workspace settings, HubSpot account settings.
- Structure observée : navigation secondaire par sections.
- Organisation : compte, boutique, plateformes, imports, sécurité, notifications, facturation future.
- Composants : forms, toggles, cards, danger zone.
- Densité : moyenne.
- Hiérarchie : paramètres fréquents en haut, danger zone isolée.
- Interactions : sauvegarde inline, confirmation destructive.
- Erreurs fréquentes : page unique interminable.
- Recommandations Climax : settings sobres et professionnels.
- Layout possible : sidebar secondaire + panneau contenu.
- À conserver : sections.
- À supprimer : options prématurées.
- À repenser : paramètres plateforme.

## Base cartes

- Références : Pokécardex, TCGplayer, Cardmarket, Collectr, PriceCharting, Ludex, eBay, Airtable gallery, Shopify products.
- Structure observée : recherche, séries, galerie, fiche carte, prix, variantes.
- Organisation : jeu, série, numéro, rareté, état, langue, prix marché.
- Composants : galerie, filtres, fiche détail, price history, table offres.
- Densité : mixte : galerie visuelle + table prix dense.
- Hiérarchie : image carte puis identification et valeur.
- Interactions : rechercher, ajouter au stock, comparer prix, voir historique.
- Erreurs fréquentes : galerie jolie mais lente, pas assez de données.
- Recommandations Climax : base cartes hybride catalogue + action vendeur `Ajouter au stock`.
- Layout possible : grid cartes, panneau filtre gauche, fiche détail drawer/page.
- À conserver : visuel cartes.
- À supprimer : fan-site non professionnel.
- À repenser : pricing vendeur.

## Authentification future

- Références : Stripe, Shopify, GitHub, Linear, Vercel, Notion, Revolut Business, Square.
- Structure observée : login simple, sécurité, reset, 2FA future.
- Organisation : email, mot de passe, session, erreurs claires.
- Composants : form, validation, alert, recovery.
- Densité : faible à moyenne.
- Recommandations Climax : sobre, confiance, sans illustration IA.

## Compte/facturation future

- Références : Stripe billing portal, GitHub billing, Vercel billing, Shopify billing, Notion billing, Ramp plans.
- Structure observée : plan, paiement, factures, usage.
- Recommandations Climax : documenter pour plus tard, ne pas construire maintenant.

## Version mobile

- Références : Revolut, Shopify mobile, Square POS, Vinted, Whatnot, Collectr, Discord, Notion Calendar, Linear mobile, Sortly, TCGplayer mobile.
- Structure observée : bottom navigation, action centrale, lists, bottom sheets.
- Organisation : Accueil, Stock, Ventes, Scan/Ajout, Plus.
- Composants : cards compactes, listes, scan, bottom sheet, alertes.
- Densité : moyenne, touch-first.
- Recommandations Climax : ne pas miniaturiser desktop ; mobile = actions rapides, consultation, scan, alertes, vente.
