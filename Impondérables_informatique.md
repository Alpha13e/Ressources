> Ce document contiendra à terme ce que j'estime nécessaire pour programmer confortablement. Cela restera élémentaire et possiblement inexact.

# Markdown
> Pour l'instant fourre-tout.

```markdown
# Ceci est un titre
## Et voilà un sous-titre degré 2
### etc...
On peut écrire du code pur `ainsi`, entre apostrophes inversées.

Pour retourner à la ligne, il faut une ligne vide.

|  ceci  |      est | un       | tableau    |
| :----: | -------: | :------- | ---------- |
| centré | à droite | à gauche | par défaut |

On peut mettre en **gras**, en *italique*;

- faire
  - des
    - listes
      - de différents degrés

1. ou numérotées
1. dynamiques
  1. échelonnées.

[ceci est le nom d'un lien](avec_le-lien.jpeg "et une description facultative")
```

Voici le résultat compilé sans les titres:

On peut écrire du code pur `ainsi`, entre apostrophes inversées.

Pour retourner à la ligne, il faut une ligne vide.

|  ceci  |      est | un       | tableau    |
| :----: | -------: | :------- | ---------- |
| centré | à droite | à gauche | par défaut |

On peut mettre en **gras**, en *italique*;

- faire
  - des
    - listes
      - de différents degrés

1. ou numérotées
1. dynamiques
  1. échelonnées. Oui j'ai écrit 3 1s !

[ceci est le nom d'un lien](avec_le-lien.jpeg "et une description facultative (hover the mouse (; )")

En fonction de l'environnement (sensible), on peut injecter des bornes html simples. La syntaxe est `<commande arguments> texte </commande>`. Il faut parfois les isoler par une ligne entière, et ils désactivent souvent la coloration syntaxique de l'éditeur.

- <u>On peut souligner avec</u> `<u>`;

<center>

Centrer avec `<center>`

</center>

<div class="alert alert-info">

Faire des boites avec `<div class="alert alert-info">`. `info` *(bleu)* est remplacable par `success` *(vert)*, `alert`, *(rouge)*, et peut-être d'autres, mais ca fonctionne rarement.

</div>

<span style="color:green">

Changer de couleur avec `<span style="color:green">`, la couleur étant changeable, à tester.

</span>

Notez que vous ne voyez pas nécessairement le résultat ici, en fonction du moteur.

## Formules MathJax/Ketex

[Ce fil stack exchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)
contient le plus gros de Mathjax.

- $\propto$: `\propto`, proportionnel
# Environnement VsCode

# Git/GitHub
> **Git** est un système de sauvegarde de fichier avec contrôle de version, toutes les modifications sont sauvegardées afin d'être capable de les annuler au besoin.

> *GitHub* est le réseau social, ou l'interface internet de Git. Il permet d'utiliser un navigateur comme interface, et de découvir facilement les projets du monde entier.

Git est très **complet**, et complexe, mais il est relativement **simple** de commencer, surtout en utilisant Github et VsCode en conjonction.

**Le principe est simple**: On utilise un **répertoire**, un super-dossier contenant des dossiers de fichiers et leur histoire ! au fil des modifications de son contenu, une **branche** se crée **(main)**. 
*Il est alors possible de s'en séparer, créer une nouvelle branche, et faire quelque chose de différent, puis, si possible, les refusionner. Utile pour la collaboration, mais on ne s'y intéressera pas.* 

1. **Se créer un compte sur GitHub**. Vous l'avez déjà fait des milliers de fois, rien de compliqué. *C'est nécessaire car toutes les entreprises y sont (ou presque, dans la tech), et y mettent des infos sensibles.*
2. Dans VsCode aller dans Source Control *(symbole de branches, 3è dans le panneau de gauche)*, et cliquer sur un bouton vous proposant de **télécharger Git** *(moyen simple de ne pas se tromper, passer par internet fonctionne)*.
3. **Créer un premier répertoire via GitHub**. Un plus est environ en haut à droite, et la page d'accueil devrait le proposer. Ajouter `readme` et `gitignore` pour la suite.
4. Recharger le panneau *source control* dans VsCode, qui détecte alors Git, et tentez de **cloner le répertoire test.** Vous devrez alors vous **connecter** à git avant de sélectionner vôtre répertoire test. Sélectionner un endroit pour le mettre sur l'ordinateur, et voilà !
5. Tentons un **commit**. Créer un fichier dans le répertoire, ou le modifier si ce n'est pas déjà fait. En le sauvegardant, sa couleur devrait changer. Toujours dans source control, il devrait apparaître comme changé. En le survolant, cliquer sur le plus (**stage** en anglais). Il est alors prêt à partir. Entrer un message de votre choix et appuyer sur le gros bouton bleu, **commit** *(on peut, dans les paramètres, le changer en Commit & sync)*. 
   
   En bas, dans la barre de statut bleue, des symboles sont visibles: le nom du répertoire et de la branche (main) suivi d'un symbole de double flèches en cercle. Il s'agit de sync, cliquer dessus. Cela synchronise l'ordinateur au cloud et est vital si un autre ordinateur participe à ce répertoire (des conflits pénibles peuvent apparaître).

Bravo, vous avez maintenant les bases pour utiliser Git seul ou peu nombreux, on a seulement effleuré la surface mais elle vous emmènera loin.

<span style="color:green">

<u>TL,DR:</u>

- **Sauvegarde** les changements:
- **Stage** (prépare à envoyer) les fichiers voulus ($+$)
- Ecrire un **message** de description
- **Commit & sync**

<center>

C'est par l'erreur qu'on apprend, surtout en informatique. 

**Soyez curieux** !

</center>

</span>

# Venvs

# Raccourcis clavier