# ERP Climax — dossier de recherche UI

Ce dossier contient un mini-site statique consultable dans GitHub, localement ou via GitHub Pages.

## Consultation locale

- Ouvrir `docs/ui-research/index.html` directement dans un navigateur.
- Aucun build, serveur, package manager ou dépendance n'est nécessaire.
- Les données structurées sont dans `references.json` et dupliquées dans `references-data.js` pour que l'ouverture locale via `file://` fonctionne sans blocage CORS.

## Publication GitHub Pages

URL attendue une fois GitHub Pages activé : `https://<owner>.github.io/<repository>/`.

Le workflow dédié `.github/workflows/ui-research-pages.yml` publie uniquement le contenu de `docs/ui-research/`. Comme l'artefact Pages a pour racine ce dossier, les chemins relatifs actuels (`styles.css`, `references-data.js`, `app.js`, `references.json`) restent compatibles avec l'URL de projet GitHub Pages.

### Procédure d'activation

1. Merger cette branche dans `main`.
2. Dans GitHub, ouvrir `Settings → Pages`.
3. Sélectionner `Source → GitHub Actions`.
4. Relancer le workflow manuellement si le premier déploiement ne démarre pas automatiquement.

Manipulation manuelle restante : `Settings → Pages → Source → GitHub Actions`.

## Contenu

- 110 références SaaS / ERP / e-commerce / finance / inventaire / analytics / mobile / seller tools.
- Filtres par type de produit, composant, device, densité, style visuel et module ERP Climax.
- Sections dédiées : Dashboard, Stock, Tableaux, Ventes, Dépenses, Rapports, Paramètres, Base cartes, Onboarding, Mobile, Navigation, Fiches détail, États vides.
- Pour chaque référence : nom, catégorie, source, statut visuel, composant observé, forces, risques, applications ERP Climax et tags.

## Politique visuelle

Le site n'embarque pas de captures inventées et ne génère pas d'images IA. Les cartes utilisent des placeholders explicites lorsque l'intégration d'une capture publique stable n'est pas suffisamment sûre. Chaque référence conserve un lien source pour consulter le visuel original.
