---
layout: single
title: "Des feuilles de style pour Sugarcube"
date: "2017-02-28 10:14:06 +0100"
categories: Twine
sidebar:
  nav: "twinery"
summary: "Vous n'aimez pas le *look* de base du format **Sugarcube** ? Moi non plus."
---
Twine utilise des *formats d'histoire*, qui déterminent à la fois l'apparence de votre récit, mais aussi la syntaxe des principales commandes et les possibilités de programmation. Nombre d'utilisateurs un peu *débrouillés* préfèrent **Sugarcube** au format par défaut, **Harlowe**. Moi aussi..  
Je vous expliquerai en détail pourquoi dans un prochain billet. 
 
Dans sa version standard, le format **Sugarcube** a une présentation en caractères blancs sur fond noir, avec une barre de navigation sur la gauche de l'écran. Cette présentation, vous pouvez la modifier à votre guise en personnalisant la feuille de style de votre histoire.  
## Modifier la feuille de style
![Sugarcube : modifier la feuille de style](/assets/images/css_sugarcube01a.jpg)  
Dans la fenêtre qui s'ouvre alors, vous pouvez entrer directement les règles de style que vous voulez modifier. Évidemment, il vaut mieux pour cela connaître au moins un peu le langage CSS 😄. Vous trouverez les références de tutoriels sur cette question en fin d'article. 

Pour savoir exactement quelles propriétés modifier, vous devrez vous reporter au manuel de **Sugarcube**. La [page consacrée aux CSS](http://www.motoslave.net/sugarcube/2/docs/css.html) vous permet de noter les classes des différents éléments d'une page Twine. Jetez un regard attentif au tableau des [exemples de sélecteurs](http://www.motoslave.net/sugarcube/2/docs/css.html#example-selectors).  

## Utiliser les outils de développement de votre navigateur
Bien évidemment, votre navigateur Internet va aussi, grâce à ses outils de développement, fournir des informations précieuses. Enregistrez votre histoire comme fichier externe, et ouvrez ce fichier de sauvegarde dans votre navigateur. Pour moi, c'est Firefox. 

Un clic droit de la souris sur le titre, la portion de texte, le menu qui vous intéresse... l'option *Examiner l'élément* vous donnera toutes les indications nécessaires en affichant l'outil **Inspecteur**.  

![Sugarcube : examiner les propriétés](/assets/images/css_sugarcube01b.jpg)  
1. L'élément à examiner : ici le titre du passage courant
2. Le fragment correspondant du code source de la page. Notre titre est balisé par `<h1>` et est un descendant de `.nuit`.
3. La règle CSS correspondante ici : `.nuit>h1 {color:white;}`

Vous pouvez faire des essais en modifiant directement les propriétés dans l'inspecteur, jusqu'à obtenir le résultat souhaité. Un clic droit sur la règle modifié : le menu déroulant vous propose de la copier dans le presse-papier. Il ne reste plus qu'à coller la règle dans la feuille de style de votre histoire sous Twine.
Sur le site du *Mozilla Developper Network*, vous trouverez une documentation très complète concernant les outils de développement, et notamment l'[inspecteur](https://developer.mozilla.org/fr/docs/Outils/Inspecteur).
