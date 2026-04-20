# Bookmarks Admin Generator

Interface statique prête pour GitHub Pages.

But : générer des blocs de code compatibles avec le dépôt `bookmarks-cih/Bookmarks`, sans modifier directement `bookmarks.love`.

## Publication GitHub Pages

1. Créer un repo GitHub nommé `bookmars-cih.github.io` ou `bookmarks-cih.github.io` selon le nom d'organisation voulu.
2. Copier `index.html` à la racine du repo.
3. Activer GitHub Pages sur la branche `main` / root.
4. Ouvrir l'URL GitHub Pages et utiliser les boutons copier.

## Où coller les blocs générés

- Onglet **Sites** : coller dans `data/bookmarks-data.js`, dans `window.BOOKMARKS_DATA = [...]`, idéalement sous le commentaire de catégorie correspondant.
- Onglet **Créateur / listing** : coller dans `creators.html`, dans `const CREATORS_DATA = [...]`.
- Onglet **Profil créateur** : dupliquer `creators/profiletemplate.html`, puis remplacer les zones `Profile Section` et `const collectionData = [...]` par les blocs générés.

L'outil ne pousse rien sur GitHub et ne touche pas à Neocities : il génère seulement du code à copier-coller.
