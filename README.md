# La Veillée

Jeu idle incrémental, cosy et pluvieux : une maison au milieu de la forêt, un feu de cheminée, des livres à lire, et des rôdeurs mignons qui tournent autour de la maison chaque nuit.

## Installer l'APK sur Android

1. Ouvre l'onglet **Releases** du dépôt et télécharge le dernier fichier `La-Veillee-1.0.N.apk`.
2. Ouvre-le sur le téléphone. Android demande d'autoriser l'installation depuis cette source : accepte pour ton navigateur ou ton gestionnaire de fichiers.
3. Les versions suivantes s'installent par-dessus la précédente, la sauvegarde est conservée.

## Comment c'est construit

- `www/index.html` : tout le jeu, en un seul fichier (code, sons synthétisés, illustrations intégrées).
- [Capacitor](https://capacitorjs.com) emballe ce fichier dans une appli Android (`android/`).
- À chaque push sur `main`, GitHub Actions construit l'APK signé et le publie dans une release (`.github/workflows/apk.yml`).

Pour mettre le jeu à jour : remplacer `www/index.html`, commit, push. L'APK suit tout seul.

La clé `android/app/laveillee.keystore` est commitée volontairement : elle garantit que chaque APK peut remplacer le précédent. Elle ne doit pas servir pour une publication sur le Play Store.

Les polices viennent de Google Fonts : sans connexion, le jeu utilise des polices de secours, tout le reste fonctionne hors ligne.
