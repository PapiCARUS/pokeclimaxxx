# UI Component Atlas — ERP Climax

## Règles globales de densité

- Desktop ERP : densité moyenne-haute, interlignes serrés mais lisibles, tables dominantes.
- Mobile : densité plus faible, actions tactiles, listes compactes, bottom sheets.
- États critiques : toujours visibles sans couleur seule.
- Les composants doivent servir le flux vendeur : identifier, comparer, agir, vérifier.

## Sidebar

- Références : Linear, Shopify Admin, GitHub, Odoo, ERPNext, Retool, Supabase, HubSpot.
- Fonctionne : labels courts, icône + texte, section active forte, regroupement par métier.
- Échoue : sidebar trop large, trop d’icônes décoratives, libellés IA vagues.
- Densité : 48 à 56 px par entrée principale, 32 à 40 px pour sous-entrées.
- États : actif, hover, disabled, badge compteur, collapse.
- Interactions : raccourcis clavier, collapse, mémoire du module actif.
- Recommandation Climax : grouper en `Pilotage`, `Ventes`, `Stock`, `Finance`, `Référentiel`, `Admin`. Garder Dashboard, Stock, Lives Whatnot, Ventes Vinted, Dépenses, Objectifs, Rapports, Paramètres, Base cartes comme entrées visibles ou sous-groupées.

## Top bar

- Références : Stripe, GitHub, Shopify, Vercel, Retool, Metabase, Ramp.
- Fonctionne : recherche globale, switcher boutique, actions rapides, statut sync.
- Échoue : top bar vide avec seulement un avatar.
- Densité : hauteur 48 à 64 px.
- États : sync OK/erreur, environnement, profil, notifications.
- Recommandation Climax : top bar = recherche, boutique active, bouton `Ajouter`, alertes stock/vente, profil.

## Navigation secondaire

- Références : GitHub tabs, Stripe sections, Shopify saved views, HubSpot object tabs, Salesforce records.
- Fonctionne : onglets par contexte, vues enregistrées, compteurs.
- Échoue : menus horizontaux trop longs.
- Recommandation Climax : Stock peut avoir `Toutes`, `À vendre`, `Réservées`, `Vendues`, `À vérifier`; Ventes peut avoir `En cours`, `Expédiées`, `Litiges`, `Archivées`.

## Breadcrumbs

- Références : GitHub, Vercel, Stripe, Supabase, Shopify.
- Fonctionne : contexte sur pages profondes.
- Échoue : breadcrumbs sur pages top-level.
- Recommandation Climax : utile pour Base cartes > Série > Carte, Stock > Lot > Carte, Paramètres > Boutique.

## KPI cards

- Références : Stripe, Ramp, Shopify, Metabase, Databox, Pennylane, Revolut Business.
- Fonctionne : titre court, valeur, période, delta, lien drill-down.
- Échoue : cartes immenses sans action, icônes décoratives, chiffres sans période.
- Densité : 4 à 6 cards max sur desktop ; 2 à 3 sur tablette ; carousel ou stack mobile.
- Recommandation Climax : CA live, marge estimée, stock immobilisé, ventes Vinted, dépenses mois, objectif mensuel. Chaque card doit ouvrir une vue filtrée.

## Tableaux

- Références : Stripe, Shopify Admin, Retool, Airtable, GitHub, HubSpot, Cardmarket, TCGplayer, ERPNext.
- Fonctionne : colonnes stables, tri, filtres, actions groupées, statut, densité.
- Échoue : lignes trop hautes, colonnes non alignées, actions invisibles, absence de sélection multiple.
- Tailles : ligne compacte 36-44 px, normale 44-52 px, header sticky.
- États : loading skeleton, empty filtered, error, selected, dirty, saved.
- Recommandation Climax : tables au cœur de Stock, Ventes, Dépenses, Base cartes. Prévoir colonnes configurables plus tard, mais démarrer opinionated.

## Filtres

- Références : Shopify saved views, GitHub issue filters, Airtable, Metabase, HubSpot, Cardmarket.
- Fonctionne : filtres visibles, chips actifs, vues sauvegardées.
- Échoue : panneau filtre massif pour 2 critères, filtres qui disparaissent.
- Recommandation Climax : filtres par plateforme, statut, période, prix, état carte, série, marge, canal.

## Recherche

- Références : Linear command menu, GitHub search, Shopify admin search, TCGplayer, PriceCharting, Pokécardex.
- Fonctionne : recherche globale + recherche locale, tolérance fautes, résultat typé.
- Échoue : simple input qui ne cherche qu’un champ.
- Recommandation Climax : recherche globale cartes/ventes/lots/acheteurs ; recherche locale dans tables.

## Onglets

- Références : GitHub, Stripe, HubSpot, Salesforce, Shopify.
- Fonctionne : onglets peu nombreux, compteurs, persistance.
- Échoue : onglets comme navigation principale entière.
- Recommandation Climax : fiche carte avec `Résumé`, `Stock`, `Historique`, `Prix`, `Notes`.

## Formulaires

- Références : Stripe settings, Shopify product editor, Odoo forms, HubSpot records, Typeform pour clarté.
- Fonctionne : sections, validation inline, aide contextuelle.
- Échoue : longues colonnes sans groupe, placeholder comme label.
- Recommandation Climax : formulaires d’ajout stock rapides, avec mode avancé replié.

## Modales

- Références : Stripe, GitHub, Shopify, Linear.
- Fonctionne : confirmation courte, action ciblée.
- Échoue : modales pour pages complexes.
- Recommandation Climax : confirmation suppression, changement statut, action rapide. Ne pas utiliser pour fiche complète.

## Panneaux latéraux / drawers

- Références : Linear, HubSpot, Intercom, Stripe, Retool.
- Fonctionne : détail sans quitter la liste, timeline, actions.
- Échoue : drawer trop étroit pour formulaire complexe.
- Recommandation Climax : fiche vente, fiche carte stock, détail dépense en drawer desktop.

## Bottom sheets

- Références : Revolut, Shopify POS, Square, Discord mobile, Collectr.
- Fonctionne : actions contextuelles mobile, filtres, détails courts.
- Échoue : reproduire une modale desktop.
- Recommandation Climax : filtres mobile, actions vente, ajout rapide, choix état carte.

## Toasts

- Références : Linear, GitHub, Shopify, Stripe, Notion.
- Fonctionne : confirmation brève avec undo.
- Échoue : toast pour erreur bloquante.
- Recommandation Climax : `Vente marquée expédiée`, `Carte ajoutée au stock`, avec annulation si possible.

## États vides

- Références : GitHub, Stripe, Shopify, Linear, Notion.
- Fonctionne : expliquer la prochaine action.
- Échoue : illustration géante IA et phrase vague.
- Recommandation Climax : empty state orienté tâche : `Ajoute ta première carte`, `Importer un fichier`, `Créer un live`.

## Erreurs

- Références : Stripe, GitHub, Shopify, Sentry.
- Fonctionne : message clair, action de résolution, code discret.
- Échoue : `Something went wrong` sans suite.
- Recommandation Climax : erreurs métier explicites : stock insuffisant, vente déjà expédiée, prix incohérent.

## Loaders

- Références : GitHub skeletons, Linear, Shopify, Stripe.
- Fonctionne : skeleton structurel.
- Échoue : spinner central permanent.
- Recommandation Climax : skeleton tables/cards ; loader inline sur action.

## Graphiques

- Références : Stripe, Metabase, Ramp, Pennylane, Databox, Power BI.
- Fonctionne : axe clair, période, comparaison, annotation.
- Échoue : donut décoratif ou chart sans décision.
- Recommandation Climax : courbes CA/marge, barres ventes par plateforme, stock immobilisé, dépenses par catégorie.

## Timelines

- Références : Stripe event timeline, HubSpot activity, Intercom conversation, GitHub activity.
- Fonctionne : horodatage, auteur, type, action.
- Échoue : timeline purement décorative.
- Recommandation Climax : historique vente, changements stock, événements live, dépenses.

## Listes d’activité

- Références : GitHub, Stripe, Linear, Shopify, HubSpot.
- Fonctionne : activité récente filtrable et reliée aux objets.
- Recommandation Climax : feed court sur Dashboard : ventes, alertes, dépenses, objectifs.

## Dashboards

- Références : Stripe, Shopify, Metabase, Ramp, Revolut Business, Datadog.
- Fonctionne : priorités claires, KPIs reliés aux actions, drill-down.
- Échoue : dashboard vitrine avec cards vides.
- Recommandation Climax : dashboard quotidien vendeur : argent, stock, ventes à traiter, alertes, prochains lives.

## Paramètres

- Références : Stripe, GitHub, Vercel, Shopify, Supabase.
- Fonctionne : navigation latérale secondaire, sections courtes.
- Échoue : tout dans une seule page.
- Recommandation Climax : Compte, Boutique, Plateformes, Import/Export, Sécurité future, Facturation future.

## Onboarding

- Références : Shopify, Square, Notion, Linear, Airtable.
- Fonctionne : checklist orientée valeur.
- Échoue : tutoriel long avant accès.
- Recommandation Climax : `Créer boutique`, `Importer stock`, `Connecter/paramétrer plateformes`, `Créer premier objectif`.

## Facturation future

- Références : Stripe Billing portal, GitHub billing, Vercel billing, Notion billing.
- Fonctionne : plan, usage, paiement, factures, annulation.
- Recommandation Climax : documenter mais ne pas implémenter maintenant.

## Mobile bottom navigation

- Références : Revolut, Square, Shopify, Vinted, Whatnot, Collectr, Discord.
- Fonctionne : 4-5 entrées max, action centrale possible.
- Échoue : copier toute la sidebar desktop.
- Recommandation Climax : `Accueil`, `Stock`, `Ventes`, `Scan/Ajout`, `Plus`.

## Galeries

- Références : Pokécardex, Collectr, TCGplayer, Vinted, Shopify products, Airtable gallery.
- Fonctionne : image, nom, série, état, prix, quantité.
- Échoue : images trop grandes sans données.
- Recommandation Climax : galerie cartes avec toggle compact/grand.

## Fiche détail

- Références : HubSpot, Stripe, Shopify product, TCGplayer card, Linear issue, Intercom user.
- Fonctionne : résumé + actions + tabs + timeline.
- Recommandation Climax : fiche carte/vente/dépense en page ou drawer selon complexité.

## Pages de reporting

- Références : Metabase, Stripe, Shopify Analytics, Ramp, Pennylane, Power BI.
- Fonctionne : filtres persistants, segmentation, export.
- Échoue : trop de graphiques sans récit.
- Recommandation Climax : rapports par période, plateforme, catégorie, marge, stock immobilisé, export CSV/PDF futur.
