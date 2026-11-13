# Computer Engineer : versions publiées

Ce dépôt ne contient que les versions publiées de **Computer Engineer**, une application où l'on construit un ordinateur complet à partir d'une seule porte logique, le NAND.

## Installer

1. Ouvre la page [Releases](../../releases/latest) et télécharge `computer-engineer-vX.Y.Z-x86_64-pc-windows-msvc.zip`.
2. Décompresse l'archive dans le dossier de ton choix, puis lance `computer-engineer.exe`.

Windows peut afficher un avertissement SmartScreen au premier lancement, car l'exécutable n'a pas de certificat de signature de code Windows. Choisis « Informations complémentaires », puis « Exécuter quand même ».

## Mises à jour

L'application cherche toute seule une nouvelle version au lancement et la propose dans un message. Chaque archive est signée (Ed25519, [zipsign](https://github.com/Kijewski/zipsign)) : l'application vérifie la signature avec sa clé publique avant de remplacer quoi que ce soit, et refuse une archive dont la signature n'est pas valide. Pour couper la recherche automatique, mets `"mises_a_jour_automatiques": false` dans `reglages.json`, dans le dossier de données de l'application.
