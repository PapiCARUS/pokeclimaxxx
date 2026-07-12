# Mobile UI Research — ERP Climax

## Positionnement

La version mobile doit être une app distincte, pas un desktop miniaturisé. Elle doit servir les moments où un vendeur est debout, en live, en déplacement, en train d’ajouter une carte, de vérifier un prix ou de marquer une vente.

## Références analysées

- Revolut : transactions, soldes, actions rapides, bottom navigation.
- Shopify mobile : commandes, produits, analytics légers.
- Shopify POS : actions tactiles, grille produits, caisse.
- Square : caisse, catalogue, rapports simples.
- Notion Calendar : navigation temporelle mobile claire.
- Linear mobile : consultation et triage, pas toutes les fonctions desktop.
- Discord mobile : navigation dense, bottom sheets, actions contextuelles.
- Vinted : annonces, messages, ventes, photo-first.
- Whatnot : live, urgence, enchères, file d’items.
- Collectr : collection portfolio, scan, valeur.
- Sortly : inventaire mobile, photos, QR.
- TCGplayer mobile : recherche cartes et prix.
- PriceCharting app : scan, collection value, search.

## Bottom navigation

- Références : Revolut, Vinted, Discord, Shopify, Collectr.
- Observation : 4 à 5 entrées max ; une action centrale peut accélérer scan/ajout.
- Recommandation : `Accueil`, `Stock`, `Ventes`, `Ajouter/Scan`, `Plus`.
- À éviter : reproduire les 9 modules desktop.

## Actions rapides

- Références : Revolut actions, Square checkout, Shopify POS, Collectr scan.
- Actions Climax prioritaires : ajouter carte, scanner/rechercher carte, créer vente, marquer expédié, ajouter dépense, vérifier prix.
- Règle : une action mobile doit prendre moins de gestes que desktop si elle est fréquente.

## Bottom sheets

- Références : Revolut, Discord, Shopify POS, Square.
- Usages Climax : filtres stock, choix état carte, statut vente, détails rapides, tri.
- À éviter : formulaires longs en sheet.

## Listes compactes

- Références : Revolut transactions, Vinted listings, Shopify orders, Discord channels.
- Recommandation : ligne = titre, sous-titre, statut, montant/quantité, image si carte.
- États : swipe action possible avec prudence, actions secondaires dans sheet.

## Cartes mobiles

- Références : Collectr portfolio cards, Shopify order cards, Vinted item cards.
- Usage : résumé vente, carte stock, KPI accueil.
- Risque : cards trop grandes empêchant la comparaison.
- Recommandation : cards compactes, image 48-72 px, données clés.

## Recherche mobile

- Références : TCGplayer, PriceCharting, Vinted, Collectr.
- Recommandation : recherche accessible en haut de Stock/Base cartes, autofocus, résultats typés.
- Fonction forte : recherche carte par nom/série/numéro, scan futur.

## Filtres mobiles

- Références : Vinted, Shopify, Cardmarket mobile patterns.
- Recommandation : chips actifs horizontaux + bottom sheet pour modifier.
- Filtres prioritaires : statut, plateforme, série, état, prix, date.

## Détail vente

- Références : Shopify orders, Vinted sale details, Stripe transaction details.
- Structure : statut, montant, produit, acheteur, timeline, actions.
- Actions : marquer expédié, ajouter tracking, contacter/notes, annuler si autorisé.

## Détail stock

- Références : Sortly, Shopify product, Collectr card detail.
- Structure : image, nom, quantité, état, prix achat/vente, emplacement, historique.
- Actions : modifier quantité, marquer vendu, ajouter à live, voir prix.

## Galerie cartes

- Références : Collectr, Pokécardex, TCGplayer, PriceCharting.
- Recommandation : deux modes : grille visuelle et liste compacte.
- Données indispensables : nom, série, numéro, rareté, prix, quantité, état.

## Consultation KPI

- Références : Revolut, Shopify, Square.
- Recommandation : accueil mobile avec 3-4 KPI maximum : ventes à traiter, CA période, dépenses, stock à vérifier.
- Graphiques : sparklines simples, pas BI complète.

## Alertes

- Références : Revolut, Shopify, Square, Discord notifications.
- Alertes utiles : vente à expédier, stock négatif, live proche, dépense inhabituelle, objectif en retard.
- Risque : notifications trop nombreuses.

## Fonctions à supprimer ou réduire sur mobile

- rapports complexes multi-graphiques ;
- paramétrage avancé ;
- imports massifs ;
- édition de colonnes ;
- comparaison lourde de tables ;
- administration future organisation/utilisateurs.

## Fonctions à garder

- dashboard court ;
- stock ;
- ventes ;
- scan/recherche carte ;
- ajout rapide ;
- détail vente ;
- détail stock ;
- alertes ;
- dépense rapide.

## Fonctions à rendre plus rapides que desktop

- scanner ou rechercher une carte ;
- ajouter une carte au stock ;
- marquer une vente expédiée ;
- ajouter une dépense avec photo ;
- vérifier un prix de carte ;
- consulter les ventes à traiter.

## Layout mobile recommandé

1. Accueil : KPI courts + tâches urgentes.
2. Stock : recherche + filtres chips + liste/galerie.
3. Ventes : tabs statut + liste actions.
4. Ajouter/Scan : action centrale.
5. Plus : Dépenses, Objectifs, Rapports simples, Paramètres limités.
