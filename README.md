# La Veillée

Un refuge sombre et pluvieux qui vit à ton heure. Une maison perdue dans la forêt, un feu à garder, un chat, un corbeau qui apporte des lettres, des livres étranges à identifier d'après le registre d'Odile, et des visiteurs qui frappent la nuit. Le matin et le soir n'offrent pas les mêmes choses. Si le feu s'éteint trop longtemps, les ténèbres prennent la maison, pièce par pièce.

## Installer l'APK sur Android

1. Ouvre l'onglet **Releases** du dépôt et télécharge le dernier fichier `La-Veillee-1.0.N.apk`.
2. Ouvre-le sur le téléphone. Android demande d'autoriser l'installation depuis cette source : accepte pour ton navigateur ou ton gestionnaire de fichiers.
3. Les versions suivantes s'installent par-dessus la précédente, la sauvegarde est conservée.

## Comment c'est construit

- `www/index.html` : tout le jeu, en un seul fichier (code, sons, illustrations intégrées).
- [Capacitor](https://capacitorjs.com) emballe ce fichier dans une appli Android (`android/`).
- À chaque push sur `main`, GitHub Actions construit l'APK signé et le publie dans une release (`.github/workflows/apk.yml`).

Pour mettre le jeu à jour : remplacer `www/index.html`, commit, push. L'APK suit tout seul.

La clé `android/app/laveillee.keystore` est commitée volontairement : elle garantit que chaque APK peut remplacer le précédent. Elle ne doit pas servir pour une publication sur le Play Store.

Les polices viennent de Google Fonts : sans connexion, le jeu utilise des polices de secours, tout le reste fonctionne hors ligne.

## Sons

Les ambiances enregistrées (pluie, feu, vent dans les arbres, hibou, tonnerre, horloge) viennent du projet open source [Moodist](https://github.com/remvze/moodist), sous licence CC0 ou Pixabay Content License. Elles ont été recoupées en boucles sans couture et intégrées au fichier du jeu. Les autres sons (boîte à musique, pages, coups à la porte, corbeau, chat, bourdon des ténèbres) sont synthétisés dans le navigateur. Les illustrations ont été générées avec ChatGPT.
