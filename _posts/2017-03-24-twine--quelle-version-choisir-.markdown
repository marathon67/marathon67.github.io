---
layout: single
title: "Twine : quelle version choisir ?"
date: "2017-03-24 15:05:51 +0100"
categories: Twine
sidebar:
  nav: "twinery"
summary: "Version en ligne ou installable ? 1.42, 2.0 ou 2.1 ?"
header:
    overlay_color: rgba(75, 75, 0, 0.5) # photo : rgba(0, 70, 0, 0.5), twine : rgba(75, 75, 0, 0.5), jekyll : rgba(0, 20, 120, 0.5), divers : rgba(0, 0, 70, 0.5)
---

{% include toc %}
> Parmi les quatre moutures de Twine disponibles à ce jour (mars 2017), je vous recommande d'installer la version **2.0.11.** Pourquoi ? C'est ce que vous découvrirez dans la suite de ce billet.

## L'ancêtre 1.4.2

La vénérable **version 1.4.2** est encore assez utilisée... mais surtout par des auteurs qui en avaient pris l'habitude, et n'ont pas voulu faire les frais de changements relativement importants dans la création de leurs histoires. Ou se passer de nombre de snippets[^snippets] et de plugins.

* Cette version n'est pas disponible pour Linux
* Les images sont incluses en Base64[^Base64] dans le code même de la page web, ce qui en limite le nombre, mais facilite la création
* Il n'est pas possible d'y installer les dernières version des formats d'histoires

{% include figure image_path="/assets/images/twine-1-42.jpg" alt="Figure 1 : l'éditeur de la version 1.4.2." caption="Figure 1 : l'éditeur de la version 1.4.2." %}

* Télécharger la version 1.4.2 [pour Windows](http://twinery.org/downloads/twine_1.4.2_win.exe) et [pour Mac](http://twinery.org/downloads/twine_1.4.2_osx.zip)
* [Mode d'emploi](http://twinery.org/wiki/twine1:reference){:target="_blank"} de la version 1.4.2

Pour quelqu'un qui débute dans la rédaction d'histoires sous Twine, **1.4.2** n'est pas, de mon point de vue, un choix  pertinent.
{: .notice--danger}

## Réellement stable : Twine 2.0.11

Cette version destinée à être installée sur votre ordinateur date un peu, mais elle a le gros avantage d'être d'une grande stabilité. Elle est disponible pour Linux, Mac et Windows.

Son seul réel défaut est un certain manque d'ergonomie et de clarté dans la construction graphique de l'arborescence. Dès que le nombre de passages (de *cases*) de l'aventure devient un peu important, l'interface est assez confuse.

Les formats d'histoire (Harlowe, Sugarcube...) livrés avec cette version ne sont pas à jour, mais il est facile d'en installer les dernières moutures.

{% include figure image_path="/assets/images/twine2-0-11.jpg" alt="Figure 2 : l'éditeur de la version 2.0.11" caption="Figure 2 : l'éditeur de la version 2.0.11." %}

* [Télécharger la version 2.0.11](http://twinery.org/){:target="_blank"} pour Linux, Mac ou Windows. Cette version est disponible en version 32 et 64 bits. Installez celle qui correspond à votre système d'exploitation.
* [Mode d'emploi](http://twinery.org/wiki/twine2:guide){:target="_blank"} des versions 2

Pour une utilisation sur votre ordinateur, Twine **2.0.11.** est la version que je recommande. Et que j'utilise moi-même.
{: .notice--danger}

## Les malheurs de la série 2.1

La série 2.1 de Twine vise à améliorer l'ergonomie du logiciel. Et effectivement, comme vous pouvez le voir ci-dessous, c'est assez réussi. Malheureusement, les versions 2.1.0 et 2.1.1 sont entachées de *bugs*, de défauts à mon sens rédhibitoires. Ils semblent surtout liés aux traductions en français, allemand... du logiciel. Vous trouverez sur le forum de [Twine](http://twinery.org/forum/) une série de conseils pour faire fonctionner malgré tout ces versions. En ce qui me concerne, rien n'y a fait. Impossible de faire tourner les Twine 2.1.x sur l'une quelconque de mes machines, que ce soit sous Linux ou Windows.

* Impossible d'enregistrer ou de charger une histoire
* Plantages récurrents, allant jusqu'à bloquer l'ordinateur
* Impossibilité de mettre à jour les formats d'histoire


{% include figure image_path="/assets/images/twine2-1.jpg" alt="Figure 3 : l'éditeur de la version 2.1" caption="Figure 3 : l'éditeur de la version 2.1." %}

En attendant que l'auteur de Twine réussisse à en éliminer les différents bugs, il est prudent d'éviter la série des  **2.1.x**.
{: .notice--danger}

## La version en ligne

La version en ligne de Twine, comme son nom l'indique, ne va pas nécessiter d'installation au sens strict du terme sur votre ordinateur. Elle s'exécute intégralement dans votre navigateur Internet, comme la capture de la figure 4 ci-dessous le montre. Aucune inscription ni enregistrement ne sont nécessaires.

* Cette version est utilisable même si vous n'avez pas le droit d'installer des logiciels
* Elle nécessite une connnexion Internet et les temps de chargement peuvent s'avérer assez longs
* La sauvegarde automatique de votre histoire se fait grâce aux possibilités de stockage local de votre navigateur
* Twine Online est toujours la dernière version disponible du logiciel

{% include figure image_path="/assets/images/twine-online.jpg" alt="Figure 4 : la version en ligne" caption="Figure 4 : la version en ligne" %}

Comme le montre la jauge cerclée de rouge sur la copie d'écran, l'espace de stockage disponible est ici limité. Gardez un œil sur la place restante et faites régulièrement des sauvegardes manuelles.

* Accéder à [Twine Online](https://twinery.org/2){:target='_blank'}

**Twine Online** rendra bien des services aux enseignants et aux animateurs qui ne sont pas *maîtres* de leurs machines. Pour des raisons de sécurité de vos fichiers, préférez néanmoins une version installable.
{: .notice--danger}

## Et pour les geeks : Twee2

[Twee2](https://dan-q.github.io/twee2/){:target="_blank"} est une approche en ligne de commande de Twine. Pour des aventures un peu longues, je vous avoue le préférer à l'original. Ce logiciel nécessite l'installation préalable du langage **Ruby** sur votre ordinateur, ce qui découragera probablement les moins aguerris.

* Possibilité d'utiliser un éditeur performant de son choix pour travailler
* Possibilité de diviser le projet en différents fichiers : css, javascript, sous-ensembles de l'histoire
* Travail collaboratif plus aisé
* Conversion automatique des fichiers Twine -> Twee2 (sauf sous Windows)

Twee2 n'est plus mis à jour depuis quelques mois. Vous trouverez dans le billet [Twee2 : mise à jour](/twine/twee2-mise-ajour/) le moyen d'y remédier.

Si vous ne craignez pas la ligne de commande, Twee2 est une alternative intéressante, qui mérite un essai.
{: .notice--danger}

[^snippets]:Fragments de code à recopier dans son propre programme pour y inclure une fonctionnalité.
[^Base64]:Forme de codage permettant, entre autres, d'inclure des données graphiques dans une page HTML sous forme de texte. Voir [l'article Wikipédia](https://fr.wikipedia.org/wiki/Base64){:target='_blank'}
