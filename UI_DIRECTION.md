# UI Direction — ERP vendeur

Date : 2026-07-11.

## Objectif

Définir des directions visuelles possibles pour un ERP/SaaS utilisé quotidiennement par des petits vendeurs Whatnot, Vinted et cartes à collectionner.

## Direction A — Dense Pro Commerce

### Style général

Interface professionnelle, claire, dense, orientée productivité. Inspiration : Shopify Admin, Stripe Dashboard, GitHub Primer.

### Densité

- Desktop : élevée, avec lignes compactes, tables riches, raccourcis et panneaux latéraux.
- Mobile : version distincte simplifiée, centrée sur consultation et actions rapides.

### Couleurs

- Fond principal : gris très clair ou blanc cassé.
- Surface : blanc.
- Texte : gris très foncé.
- Accent : bleu ou indigo sobre pour actions primaires.
- Statuts : vert, orange, rouge, violet avec labels discrets.

### Typographie

- Sans-serif système ou Inter.
- Tailles compactes : 12–14 px pour tables, 14–16 px pour contenu, 20–28 px pour titres.

### Radius

- 6 à 10 px.
- Peu de formes très arrondies.

### Ombres

- Très légères.
- Préférer bordures et surfaces plutôt qu’ombres fortes.

### Navigation

- Sidebar persistante à gauche.
- Topbar avec recherche globale, boutique active, notifications, profil.
- Favoris/vues sauvegardées sous les modules principaux.

### Cartes

- Cartes KPI compactes.
- Cartes d’alerte avec action directe.
- Peu de cartes décoratives.

### Tableaux

- Élément central du produit.
- Colonnes configurables.
- Densité réglable.
- Filtres sauvegardés.
- Actions bulk.

### Formulaires

- Sections explicites.
- Validation inline.
- Panneau latéral pour édition rapide.
- Page complète pour création complexe.

### Mobile

- Bottom navigation.
- Dashboard simplifié.
- Actions rapides : ajouter vente, ajouter dépense, scanner/rechercher carte, voir stock faible.
- Bottom sheets pour filtres et actions.

### Avantages

- Très adapté à un usage quotidien.
- Bon équilibre entre sérieux, efficacité et accessibilité.
- Compatible avec HTML/JS actuel et future migration progressive.

### Risques

- Peut paraître moins “premium” si le détail visuel est négligé.
- Nécessite une vraie discipline de composants.

## Direction B — Command Center Premium

### Style général

Interface plus premium et analytique, inspirée Linear, Vercel, Revolut Business.

### Densité

- Desktop : moyenne à élevée.
- Plus d’espace que Direction A.
- Focus fort sur dashboards, statuts, timelines et interactions rapides.

### Couleurs

- Fond : gris très sombre ou clair selon thème.
- Accent : violet, bleu électrique ou vert premium.
- Statuts : pastels maîtrisés.

### Typographie

- Inter, Geist ou équivalent.
- Titres plus expressifs.
- Hiérarchie forte.

### Radius

- 10 à 14 px.
- Cartes plus modernes.

### Ombres

- Ombres douces, effets de profondeur modérés.
- Possibilité de thème sombre plus tard.

### Navigation

- Sidebar compacte.
- Palette de commandes centrale.
- Recherche et actions rapides très visibles.

### Cartes

- Widgets modulaires.
- Cartes KPI avec micro-graphes.
- Timeline d’activité.

### Tableaux

- Moins bruts, plus éditoriaux.
- Risque de densité insuffisante si mal conçu.

### Formulaires

- Modales/panneaux latéraux.
- Flows guidés.
- Stepper pour imports ou onboarding.

### Mobile

- Très bon potentiel pour consultation premium.
- À limiter aux actions rapides.

### Avantages

- Produit plus différenciant.
- Peut donner une impression SaaS moderne forte.
- Adapté aux dashboards et rapports.

### Risques

- Peut sacrifier la densité nécessaire au stock et aux ventes.
- Plus coûteux à maintenir.
- Risque d’interface “jolie mais lente”.

## Direction C — Inventory Studio / Card Gallery

### Style général

Interface hybride entre ERP dense et collection manager visuel. Inspiration : Notion gallery, Collectr, Shopify products, outils de catalogue.

### Densité

- Desktop : densité modulable selon vue.
- Table pour gestion de masse.
- Galerie pour base cartes et stock visuel.

### Couleurs

- Palette neutre.
- Accents par type : Pokémon, sport, sealed, graded, vente, live.
- Attention à ne pas rendre l’interface trop ludique.

### Typographie

- Sans-serif lisible.
- Éviter les polices gaming/collection.

### Radius

- 8 à 12 px.
- Cartes visuelles un peu plus arrondies.

### Ombres

- Légères sur cartes/galerie.
- Bordures sur tables.

### Navigation

- Modules ERP classiques.
- Dans stock/base cartes : bascule Table / Galerie / Liste.

### Cartes

- Cartes produits/cartes TCG avec image, rareté, quantité, coût, prix, marge.
- Badges pour état et plateforme.

### Tableaux

- Toujours présents pour productivité.
- La galerie ne doit pas remplacer la table.

### Formulaires

- Édition rapide depuis galerie.
- Ajout rapide de carte/stock.

### Mobile

- Très adapté à la consultation de collection.
- Scanner, recherche, favoris, stock faible.

### Avantages

- Très aligné avec le marché cartes à collectionner.
- Rend la base cartes plus attractive.
- Permet un produit distinctif.

### Risques

- Peut détourner l’attention des modules ERP sérieux.
- Nécessite une bonne gestion images/performance.

## Recommandation

Recommandation principale : Direction A — Dense Pro Commerce, enrichie par des éléments ciblés de Direction C pour la base cartes et la galerie.

Pourquoi :

1. L’ERP sera utilisé quotidiennement ; la vitesse, la lisibilité et la densité priment.
2. Les modules stock, ventes, dépenses, objectifs et rapports nécessitent tables, filtres et actions bulk.
3. Une interface trop premium/animée risque de ralentir la saisie et la maintenance.
4. La base cartes mérite une expérience visuelle spécifique, mais elle ne doit pas dicter tout le produit.

Décision visuelle proposée :

- Base générale : Dense Pro Commerce.
- Accent différenciant : galerie cartes et vues collection.
- Mobile : application de consultation/actions rapides, pas réduction du desktop.
