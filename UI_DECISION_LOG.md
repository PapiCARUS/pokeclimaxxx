# UI Decision Log — ERP Climax

## Décisions émergentes validées provisoirement

1. **Direction générale** : outil vendeur opérationnel plutôt que dashboard marketing.
2. **Densité desktop** : moyenne-haute, particulièrement pour Stock, Ventes, Dépenses et Rapports.
3. **Mobile** : app distincte, simplifiée, pensée autour d’actions rapides.
4. **Tables** : composants centraux de l’ERP, avec filtres, tri, statuts, bulk actions et drawer détail.
5. **Base cartes** : nécessite une interface hybride galerie + données denses.
6. **Dashboard** : doit prioriser tâches vendeur, alertes et argent réel, pas métriques vanity.
7. **Visual direction recommandée** : hybride ERP + marketplace cartes, sur base B2B sobre.

## Éléments rejetés

1. Interface trop vide façon template SaaS.
2. Grands gradients décoratifs.
3. Cards KPI sans action.
4. Icônes décoratives systématiques.
5. Mobile réduit au desktop.
6. Sidebar avec tous les modules non groupés si elle devient trop longue.
7. Graphiques décoratifs sans décision associée.

## Points ouverts

1. Mode clair seul ou clair + sombre.
2. Accent couleur principal.
3. Densité compacte par défaut ou option de densité.
4. Place de la galerie dans Stock vs Base cartes.
5. Niveau de personnalisation des vues.
6. Choix futur de bibliothèque data grid.
7. Design system custom ou web components existants.
8. Gestion future de la facturation dans l’IA visuelle globale.

## Contradictions entre références

### Stripe/Ramp vs Cardmarket/PriceCharting

- Stripe/Ramp : premium, propre, confiance.
- Cardmarket/PriceCharting : denses, spécialisés, parfois datés.
- Décision actuelle : prendre la rigueur premium, garder la densité spécialisée, éviter le look daté.

### Vercel/Notion vs Retool/Shopify

- Vercel/Notion : espace, minimalisme, calme.
- Retool/Shopify : opération, tables, actions.
- Décision actuelle : Climax doit pencher Retool/Shopify pour les pages métier, avec sobriété Vercel uniquement pour settings/auth.

### Collectr vs ERP classiques

- Collectr : mobile, portfolio, visuel carte.
- ERPNext/Odoo : profondeur métier.
- Décision actuelle : desktop ERP dense, mobile inspiré Collectr/Revolut/Square.

### Whatnot live vs pages de gestion

- Whatnot : urgence, vidéo, flux événementiel.
- ERP : calme, vérification, traçabilité.
- Décision actuelle : créer un mode live/focus séparé plutôt que contaminer toute l’UI.

## Questions à trancher plus tard

1. Les vendeurs veulent-ils un mode sombre pour les lives ?
2. Le stock est-il majoritairement cartes individuelles, lots, produits scellés ou mélange ?
3. Faut-il une notion d’emplacement physique dès la première refonte ?
4. Le mobile doit-il inclure scan photo dès la V1 ?
5. Quels exports sont indispensables : CSV, PDF, Excel ?
6. Quelle est la priorité entre Base cartes et Stock opérationnel ?
7. Quels modules doivent être visibles dans la première navigation ?

## Hypothèses actuelles

1. Les utilisateurs sont de petits vendeurs qui veulent gagner du temps, pas administrer un ERP complexe.
2. Les pages les plus utilisées seront Stock, Ventes/Lives, Dashboard et Base cartes.
3. La confiance vient de la précision et de la lisibilité, pas d’effets visuels.
4. Le mobile sera utilisé pour actions rapides, pas reporting complet.
5. La refonte doit créer une identité Climax : vendeur, carte, marketplace, finance simple.
