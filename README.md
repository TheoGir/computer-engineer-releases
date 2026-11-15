# Computer Engineer

Computer Engineer fait construire un ordinateur complet à partir d'une seule porte logique, la
NAND. Ce guide dit comment l'installer, s'en servir et régler les problèmes. Dans
l'application, **F1** ouvre la même aide.

Ce dépôt ne contient que les versions publiées : chaque [version](../../releases) porte son archive signée et la liste de ses nouveautés.

## Installer

1. Télécharge la dernière archive sur la page des versions :
   <https://github.com/TheoGir/computer-engineer-releases/releases/latest>
   (`computer-engineer-vX.Y.Z-x86_64-pc-windows-msvc.zip`).
2. Extrais-la dans un dossier à toi (clic droit, « Extraire tout »), par exemple
   `Documents\Computer Engineer`. Ne lance pas l'application depuis l'archive sans l'extraire.
3. Lance `computer-engineer.exe`. Au tout premier lancement, Windows peut afficher
   « Windows a protégé votre ordinateur » : l'exécutable n'est pas signé par un certificat
   payant. Clique sur « Informations complémentaires », puis « Exécuter quand même ».
4. L'application pose un raccourci sur le bureau et dans le menu Démarrer (réglable dans les
   paramètres).

Rien d'autre à installer : ni droits d'administrateur, ni bibliothèque.

## Mises à jour

L'application cherche une nouvelle version à chaque lancement. Si elle en trouve une, un
message propose « Mettre à jour » : elle la télécharge, **vérifie sa signature** avant de
remplacer quoi que ce soit, puis propose de redémarrer. Paramètres : couper la recherche
automatique, ou « Chercher maintenant ». Une version plus récente ouvre toujours les projets
des plus anciennes ; l'original d'un projet mis au nouveau format est gardé dans
`avant-migration`.

## Premiers pas

- **L'accueil** : « Continuer » (ou Entrée) reprend le dernier projet ; le parcours des
  quêtes ; tes projets ; les paramètres.
- **L'atelier** : glisse des portes NAND, des interrupteurs et des lampes depuis la palette,
  tire des fils entre les points de connexion, clique sur les interrupteurs. Le courant se
  propage porte après porte : allumé (1), éteint (0), inconnu ou en conflit (X), non piloté (Z).
- **Les briques** : sélectionne plusieurs éléments (Maj + glisser), puis Ctrl+G. La brique va
  dans la palette ; double-clic pour entrer dedans, Échap pour remonter.
- **Les quêtes** : de la porte NON jusqu'à plusieurs ordinateurs, et des grands projets.
  « Vérifier » compare ton circuit à un corrigé prouvé ; chaque réussite devient une brique.
- **L'ordinateur miniature** : dans tes projets, ouvre l'exemple « Ordinateur miniature ».
  Clique sur son clavier et tape deux chiffres : il affiche leur produit.

## Programmer l'ordinateur

Dans l'ordinateur miniature, **Ctrl+P** ouvre le programme de sa mémoire morte. Écris en
assembleur (F1, « Programmer l'ordinateur », liste les seize instructions), puis « Charger
dans la mémoire » : la mémoire morte est refabriquée en portes NAND et l'ordinateur
redémarre avec ton programme. Exemple, qui écrit `HI` :

```
        LDI 'H'
        OUT
        LDI 'I'
        OUT
fin:    HLT
```

## Raccourcis

| Touche | Effet |
|---|---|
| F1 | aide |
| Espace | lecture ou pause |
| Ctrl+Z / Ctrl+Y | annuler / rétablir |
| Ctrl+A, Ctrl+G, Ctrl+D | tout sélectionner, regrouper en brique, dupliquer |
| Ctrl+P | programme de la mémoire morte |
| Suppr | supprimer |
| Échap | lâcher la sélection, puis remonter d'une brique |
| F, flèches, molette | recadrer, déplacer la sélection, zoomer |

## Tes fichiers

Tout s'enregistre tout seul, une seconde après chaque modification, dans
`%APPDATA%\Computer Engineer` (Mes projets, « Ouvrir le dossier ») : `projets`, `corbeille`,
`parcours.json` (quêtes réussies), `reglages.json`, `avant-migration`, `rapports`. Pour
sauvegarder ou changer d'ordinateur, copie ce dossier.

## En cas de problème

- **La fenêtre ne s'ouvre pas** : un message explique pourquoi. Le plus souvent, le pilote de
  la carte graphique est trop ancien : mets-le à jour (Windows Update ou le site du fabricant).
- **« Computer Engineer est déjà ouvert »** : une seule fenêtre à la fois, pour que deux
  fenêtres n'écrasent pas les mêmes projets. Cherche l'autre dans la barre des tâches.
- **L'application s'est arrêtée brusquement** : au lancement suivant, un message propose
  « Voir le rapport ». Le projet avait été enregistré juste avant. Le rapport (dossier
  `rapports`) ne contient aucun de tes projets ; tu peux l'envoyer pour aider à corriger.
- **Un projet « illisible »** : s'il vient d'une version plus récente, mets l'application à
  jour ; il n'a pas été modifié. S'il est abîmé, il reste dans `projets`, où l'on peut le
  réparer à la main (JSON lisible).

## Désinstaller

Supprime le dossier où tu as extrait l'application, puis les raccourcis du bureau et du menu
Démarrer. Tes projets restent dans `%APPDATA%\Computer Engineer` : supprime aussi ce dossier
si tu ne veux pas les garder.
