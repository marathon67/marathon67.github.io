---
title: 'Twee2 : mise à jour'
layout: single
date: '2017-03-07 14:58:48 +0100'
categories: Twine
summary: Twee2 est un outil bien sympathique, mais plus mis à jour depuis quelques
  mois. Voyons comment y remédier.
sidebar:
  nav: twinery
header:
  overlay_color: rgba(75, 75, 0, 0.5)
---

{% include toc %}
Je me suis quelque peu énervé avec les dernières versions de *Twine*, les 2.1 et 2.1.1. Impossible de les faire tourner convenablement sur l'un quelconque de mes ordinateurs, que ce soit à la maison ou au bureau. Sous Linux ou Windows. Je me suis même laissé aller à un commentaire peu amène sur le forum...

## Pourquoi Twee2 ?
Du coup, j'en reviens à [Twee2](https://dan-q.github.io/twee2/). En gros, il s'agit d'un compilateur en ligne de commande pour des jeux Twine. Il présente quelques avantages en terme de souplesse d'utilisation :

* Possibilité de scinder l'aventure en fichiers multiples
* Facilité d'un travail collectif dans un dépôt Github
* Utilisation possible de *Sass* pour les feuilles de style
* Utilisation possible de *Coffeescript* pour le javascript
* Édition du code dans Atom, autrement plus confortable que l'éditeur des passages dans *Twine*

Pour peu que *Ruby* soit installé sur votre machine, rien de plus simple que d'installer *Twee2* :
~~~~~
$ gem install twee2
~~~~~
Remarquez que je n'ai pas utilisé `sudo`. Car installer des *gems* au niveau du système peut poser de sérieux problèmes de sécurité. Je reviendrais sur l'installation de *Ruby* dans un billet ultérieur.

### Les soucis

Si vous compilez en l'état un fichier *Twine*, vous allez avoir deux problèmes :

* L'auteur de *Twee2*, **Dan-Q** a choisi de ne pas traiter des passages aux noms spéciaux, comme **StoryMenu**. Ils étaient utilisés dans *Twine 1.4*, abandonnés dans les premières versions de *Sugarcube*, puis réintroduits dans les plus récentes.
* La version de *Sugarcube* utilisée n'est pas non plus à jour. Les dernières livraisons ont apporté quelques ajouts que j'apprécie de pouvoir utiliser, comme la macro `<<capture>>`.

### Où est Twee2 ?

Pour réaliser cette mise à jour, il faut d'abord localiser où est installé *Twee2* sur votre ordinateur. La procédure est identique sous *Windows* et *Linux*, seuls les noms des dossiers vont changer. Ouvrez un terminal de commande et entrez :
~~~
$ gem env
~~~
Vous obtiendrez un écran qui va ressembler à ceci :


![Gem : où est installé Twee2 ?](/assets/images/twee2.jpg)

*Twee2* se trouve dans l'un des dossiers intitulés **INSTALLATION DIRECTORY** ou **USER INSTALLATION DITECTORY**. Ouvrez les l'un après l'autre jusqu'à repérer notre *gem Twee2*.

![Twee2 : mon dossier d'installation](/assets/images/twee2a.jpg){: .align-left}
Deux fichiers sont ici à remplacer `format.js` et `story_file.rb`.

### Mettre à jour Sugarcube
Le premier fichier, `format.js` est simplement la dernière version de *Sugarcube2*. Pour mettre à jour :

* Allez sur le site de [Sugarcube](http://www.motoslave.net/sugarcube/2/)
* Dans la section **Downloads**, récupérez l'archive de la dernière version pour *Twine 2.0*. Au 7/03/17, c'est la [V2.14](http://www.motoslave.net/sugarcube/download.php/2/sugarcube-2.14.0-for-twine-2.0-local.zip).
* Décompressez l'archive sur votre ordinateur
* Remplacez le fichier `format.js` dans le dossier *Sugarcube2* de votre installation de *Twee2* par celui extrait de l'archive. Et voilà.

### Prise en compte des noms de passage spéciaux

Sur le [dépôt Github](https://github.com/Dan-Q/twee2) de *Twee2*, un utilisateur, **MCDemarco** a posté une modification du logiciel permettant de faire accepter les noms de passage spéciaux comme *StoryMenu*. Malheureusement, **Dan-Q**, ne l'a pas prise en compte pour l'instant. Nous allons le faire nous-mêmes, *à la main*.

* Copiez le contenu du fichier ci-dessous (après avoir cliqué sur **view raw**)
* Ouvrez le fichier `story_file.rb` présent sur votre ordinateur
* Remplacez-y le code d'origine par celui que vous venez de copier. Enregistrez. Et voilà...
* Vous pouvez également télécharger ce fichier sous forme d'archive en cliquant sur *story_file.rb* en bas du cadre de code.

<script src="https://gist.github.com/marathon67/004c5e88cadc7a8cb2e51a18a6a59f84.js"></script>

## Si ! Ça marche
Et pour vous montrez que tout ça fonctionne de façon satisfaisante, j'ai mis sur *Github* un dépôt contenant la version à la sauce *Twee2* de mon démonstrateur [Le mini-monde](https://github.com/marathon67/m_monde-twee2).

Mes excuses enfin aux lecteurs pour lesquels une bonne partie de cet article n'était que charabia indigeste. J'écris mes billets suivant deux rythmes, deux planifications différentes.
 Il y a d'abord ceux d'actualité : une manip' que je viens de mener, une découverte du moment que j'ai envie de partager.
 Il y a (aura) aussi des billets à la parution plus *raisonnée*, plus pédagogique, prenant les choses par leur commencement. Je reviendrais donc dans cette série là sur l'installation de *Ruby* ou le choix des formats d'histoire pour *Twine*.
