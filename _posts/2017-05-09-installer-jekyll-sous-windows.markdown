---
published: false
title: "Installer Jekyll sous Windows"
date: "2017-05-09 17:36:34 +0200"
layout: single
categories: Jekyll
sidebar:
  nav: "jekyll"
summary: "Jekyll est très utilisé chez les Linuxiens, mais fonctionne aussi sous Windows."
header:
  overlay_color: rgba(0, 20, 120, 0.5) # photo : rgba(0, 70, 0, 0.5), twine : rgba(75, 75, 0, 0.5), jekyll : rgba(0, 20, 120, 0.5), divers : rgba(0, 0, 70, 0.5)
---

{% include toc %}

> Je vais vous proposer ici d'installer sous Windows non seulement le générateur de sites statiques **Jekyll**, mais aussi deux outils complémentaires, **Git**, gestionnaire de versions et **Atom**, outil avancé d'édition de programmes et de sites web. En un mot, un *atelier Jekyll* complet.

## Prélude : installer Ruby

**Jekyll** est un logiciel développé avec le langage de programmation **Ruby**. Relativement récent, **Ruby** est présent par défaut sur les systèmes Mac et Linux, mais pas sous Windows. Il nous faudra donc commencer par installer  **Ruby**. Ce sera aussi l'occasion de nous remettre à utiliser la bonne vieille fenêtre de commandes.

Rendez-vous sur le site de **[Ruby](https://rubyinstaller.org/downloads/){:target="_blank"}** et téléchargez la dernière version de *Ruby-installer pour Windows 64*. Téléchargez également la version correspondante du *Ruby Dev-kit*, en bas de la même page web.

## Installer Jekyll
Dans une fenêtre de commandes, tapez :
```
gem install jekyll
```
Vérifiez votre installation, toujours dans la fenêtre de commandes :
```
jekyll --version
```

## Installer Git pour Windows
**Git** est un logiciel intimement lié au développement de Linux : il a été développé initialement par *Linus Torvalds*, le père de l'OS libre il y a une dizaine d'années. Pour faciliter le travail collaboratif sur Linux.

### Github Desktop

## Installer Atom
**Atom** est lui aussi une production de Github. Un bon équilibre, ce me semble, entre la richesse des fonctionnalités et une relative facilité d'emploi. Il dispose de *packages*, de modules additionnels, pour la plupart des besoins de l'*atelier Jekyll* et peut s'installer à l'identique sur les différents systèmes d'exploitation.

### Et quelques packages
Pour installer des Packages dans Atom :

* Cliquez sur `Edit -> Preferences` (ou Settings) :
* Les préférences s'affichent comme un nouveau document.
* Dans ce pseudo-document, à gauche, cliquer sur `+ Install`.
* Dans le champ de recherche **(1)**, tapez `Jekyll` puis cliquez sur `Packages`.
* Les Packages pertinents sont affichés **(2)** : faites votre choix.
* Une fois la sélection des Packages terminés, sauvegardez et fermez les préférences : `CTRL-S` puis `CTRL-W`.

{% include figure image_path="/assets/images/atom01.jpg" alt="Figure 4 : Installer des Packages dans Atom." caption="Figure 4 : Installer des Packages dans Atom." %}

Installez les Packages suivants dans Atom :
* Pour **Jekyll** : *jekyll* et *language-liquid*
* Pour **Markdown** : *language-markdown* et *markdown-writer*
* Pour **Git** : *git-plus*
