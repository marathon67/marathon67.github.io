---
title: "Traduire Sugarcube"
layout: single
categories: Twine
sidebar:
  nav: "twinery"
summary: "Ce format d'histoire a une interface utilisateur assez conséquente : affichons-la en français"
---
## Une interface étudiée pour la traduction
L'interface de **Sugarcube2** est facile à traduire, car programmée spécifiquement pour cela. Toutes les chaînes de caractères qui en forment le texte sont codées sous forme de variables *Javascript*. Si vous lisez l'anglais, je vous invite à voir ce qu'en dit la [documentation officielle](http://www.motoslave.net/sugarcube/2/docs/localization.html).

Dans le code de **Sugarcube2** ces variables correspondent au fichier [strings.js](https://bitbucket.org/tmedwards/sugarcube/src/v2-release/src/l10n/strings.js). Je vous en propose une traduction en français que vous trouverez dans le *gist*[^gist] ci-dessous. Libre à vous, bien entendu, de la modifier ou de l'amender.
Rien de plus simple ensuite que de mettre cette traduction en place dans votre histoire.

[^gist]:Le *gist* est un fragment de code réutilisable et mis à la disposition du public sur Github. Il est facile à insérer dans une page web où il propose coloration syntaxique, numérotation des lignes et accès au texte brut.

## Ma traduction

<script src="https://gist.github.com/marathon67/9402b7fc34bac992f3f937cdc9c6a049.js"></script>

## Installer la traduction

* Affichez le code en format brut. Comme pour tous les *Gists*, le plus pratique est de cliquer, en bas à droite de la fenêtre de code, sur `view raw`. Le code s'affiche dans un nouvel onglet, sans aucune mise en forme.

* Sélectionnez par `CTRL-a` et copiez par `CTRL-c`.

* Dans **Twine**, affichez l'histoire que vous voulez doter d'un format **Sugarcube2** en français.

![La fenêtre Javascript de Twine](/assets/images/twine-javascript_2.jpg)


* Ouvrez la fenêtre Javascript comme montré dans l'illustration précédente.
* Collez la traduction française de l'interface : le raccourci clavier est ici obligatoire : `CTRL-v`. Attention à ne pas écraser des lignes de code existantes, si vous en avez déjà insérées.

## Et voilà !

La copie d'écran ci-dessous vous montre le résultat obtenu dans mon démonstrateur [Mini-monde](https://www.bac-a-sable.eu/mini-monde/) en effectuant les opérations précédentes.

![L'interface en français](/assets/images/twine-javascript_1.jpg)
