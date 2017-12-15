---
published: true
title: "Votre atelier Jekyll sous Windows"
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

> Je vais vous proposer ici d'installer sous Windows non seulement le générateur de sites statiques **Jekyll**, mais aussi deux outils complémentaires, **Git**, gestionnaire de versions et **Atom**, outil avancé d'édition de programmes et de sites web. En un mot, un *atelier Jekyll* complet. Il y faudra un peu plus de trois clics...
> Ce billet s'inspire partiellement d'un article de Sverrir Sigmundarson [Jekyll 3 on Windows](https://labs.sverrirs.com/jekyll/){:target="_blank"}.

## Prélude : installer Ruby

**Jekyll** est un logiciel développé avec le langage de programmation **Ruby**. Relativement récent, **Ruby** est présent par défaut sur les systèmes Mac et Linux, mais pas sous Windows. Il nous faudra donc commencer par installer  **Ruby**. Ce sera aussi l'occasion de nous remettre à utiliser une bonne vieille fenêtre de commandes.

Rendez-vous sur le site de **[RubyInstaller](https://rubyinstaller.org/downloads/){:target="_blank"}** et téléchargez la dernière version de la série 2.2 de *Ruby-installer pour Windows 64*. Début juin 2017, il s'agit de *Ruby 2.2.6 (x64)*. Téléchargez également la version correspondante du *Ruby Dev-kit*, en bas de la même page web.

Installez **Ruby** de la façon habituelle : lancez l'installeur par un double clic. Deux points de détails à respecter cependant :
* Choisissez un dossier d'installation dont le nom ne comprend pas d'espace (Plutôt `C:\Ruby` que `C:\Program Files\Ruby`)
* Dans la boîte de dialogue initiale, si elle est visible, cochez la case `Add Ruby executables to your PATH`.

{% include figure image_path="/assets/images/rubyinstaller.png" alt="Figure 1 : Installer Ruby." caption="Figure 1 : Installer Ruby." %}

### Ruby DevKit
Le Ruby DevKit est un ensemble d'utilitaires dont nous aurons besoin pour faire fonctionner Jekyll.
Le fichier que vous avez téléchargé plus haut est une archive auto-extractible. Cliquez deux fois pour lancer sa décompression. Là aussi, vous choisirez un dossier dont le nom ne comporte pas d'espace. Par exemple `C:\RubyDevKit\`.

Il faut maintenant initialiser le DevKit et le lier à votre installation de Ruby.

#### Fenêtre de commandes Windows
Les étapes suivantes passent par l'utilisation de la fenêtre de commandes Windows. Pour la lancer :
* Allez dans le *Menu démarrer*
* Repérez le champ *Rechercher les programmes et fichiers*
* Tapez-y `cmd` : Windows vous propose, en haut du menu `cmd.exe`
* Cliquez deux fois sur `cmd.exe` pour lancer la fenêtre de commandes
* Repérez l'icône correspondante dans la barre des tâches, en bas de votre écran. Faites-y un clic-droit et sélectionnez `Attacher à la barre des tâches`. Ceci vous permettra d'accéder très rapidement à la fenêtre de commandes.

Suivant votre version de Windows, vous pouvez également ouvrir le navigateur de fichiers, aller dans le dossier voulu et y faire un `Majuscule+Clic Droit`. Vous verrez alors apparaître un item de menu `Ouvrir une fenêtre de commandes ici`.
{: .notice--danger}

{% include figure image_path="/assets/images/cmd.png" alt="Figure 2 : La fenêtre de comandes Windows." caption="Figure 2 : La fenêtre de comandes Windows." %}

#### Initialiser le DevKit

Ouvrez la fenêtre de commandes Windows et allez dans le dossier où vous avez extrait le DevKit puis initialisez-le.

```
cd C:\RubyDevKit
ruby dk.rb init
```

Vérifiez que l'initialisation du DevKit s'est faite sans erreur :

`ruby dk.rb review`

Complétez maintenant l'instllation en liant le DevKit à votre version de Ruby.

`ruby dk.rb install`

Chaque fois que, comme ici, vous utilisez des commandes qui vont modifier les chemins de recherche de Windows, le *Path*, il est nécessaire de fermer puis de réouvrir la fenêtre de commandes. Sans quoi elle ne prendra pas en compte les nouveaux chemins, et vous obtiendrez des messages d'erreur.
{: .notice--danger}

## Installer Jekyll
Dans une fenêtre de commandes, tapez :
```
gem install jekyll bundler
gem install wdm

```
L'utilitaire **wdm** permet de mettre à jour automatiquement votre serveur web local, pour y voir les modifications apportées aux pages votre site en temps réel.

Vérifiez enfin votre installation, toujours dans la fenêtre de commandes :
```
jekyll --version
```
Si tout se passe bien, vous pouvez maintenant sauter la section suivante et aller directement à [Installer Git pour Windows](#installer-git-pour-windows).

### Erreur SSL

Il est possible que votre première installation d'un fichier .gem échoue, avec un message dans votre fenêtre de commandes similaire à celui-ci :
```
ERROR: Could not find a valid gem 'jekyll' (>= 0), here is why:
Unable to download data from https://rubygems.org/
- SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed (https://rubygems.org/latest_specs.4.8.gz)
```
Il s'agit d'un bug dans l'établissement d'une liaison sécurisée avec le dépôt officiel des fichiers .gem. Pour le corriger, il faudra installer manuellement une mise à jour.

#### Télécharger rubygems-update
Vous devez tout d'abord déterminer votre version de RubyGems en entrant `gem -v` dans votre fenêtre de commande Windows. Seuls les deux premiers chiffres sont à retenir. Par exemple si `gem -v` vous renvoie `2.5.1`, vous retiendrez seulement `2.5`

Allez sur la page des [rubygems-update](https://rubygems.org/gems/rubygems-update/versions){:target="_blank"} et repérez dans la liste l'entrée la plus récente correspondant à votre version. Ici, ce serait :

```**2.5.2** - February 01, 2016 (464 KB)```

Cliquez sur le lien correspondant à cette version de rubygems-update. Il vous consuit à une page présentant en détails cette version de
RubyGems. Sur la droite de cette page repérez une barre de navigation latérale proposant une liste de liens.
Cliquez sur `Download` et sauvegardez le fichier .gem, par exemple sous `C:\rubygems-update-2.5.2.gem` (pas d'espace dans le nom de dossier !).

#### Mettre à jour rubygems

Entrez les commandes suivantes dans votre fenêtre de commandes Windows :

```
cd C:
gem install --local rubygems-update-2.5.2.gem
```

Fermez, puis rouvrez votre fenêtre de commandes. Ceci fait, vous pouvez maintenant recommencer la séquence installer **Jekyll** comme indiqué plus haut.

## Installer Git pour Windows
**Git** est un logiciel intimement lié au développement de Linux : il a été développé initialement par *Linus Torvalds*, le père de l'OS libre il y a une dizaine d'années. **Git** est un logiciel de contrôle de versions : il vous permet de gérer les différents étapes de la construction de votre projet et de revenir en arrière à tout moment. **Git** facilite grandement le travail coopératif. Il est disponible sous Linux, Mac et Windows.

[Téléchargez](https://git-scm.com/download/win){:target="_blank"} le logiciel et installez-le de la façon habituelle. Il faudra porter attention à quelques options durant le processus d'installation.

{% include figure image_path="/assets/images/git2.png" alt="Figure 3 : Git pour Windows - Options." caption="Figure 3 : Git pour Windows - Options." %}

Dans les panneaux suivants, validez également les options :
* Use Git from GitBash only
* Checkout Windows-style, commit Linux-style line endings
* Enable file system caching
* Enable Git Credential Manager


## Installer Atom
**Atom**, logiciel à mi-chemin entre l'éditeur de code et l'IDE[^ide], est lui aussi une production de Github. Un bon équilibre, ce me semble, entre la richesse des fonctionnalités et une relative facilité d'emploi. Il dispose de *packages*, de modules additionnels, pour la plupart des besoins de l'*atelier Jekyll* et peut s'installer à l'identique sur les différents systèmes d'exploitation : Linux, Mac et Windows.
[Téléchargez](https://atom.io/){:target="_blank"} et installez le logiciel de la façon habituelle. Attention, le processus est un peu long.

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

**Atom 1.18** (encore en beta fin mai 2015 - [téléchargement](https://atom.io/beta){:target="_blank"}) propose une intégration accrue avec Git et Github comme vous pouvez le voir ci-dessous. La totalité des opérations courantes de contrôle de version et de publication en ligne peuvent se faire sans quitter Atom et donc sans fenêtre de commande ou terminal.  Inutile avec cette version d'installer le package *git-plus*.
Je n'y ai pas trouvé de bug gênant malgré une utilisation intensive (mais je travaille avant tout sous Linux...) et vous conseille donc cette version-là pour sa simplification du *workflow*.
{: .notice--danger}

{% include figure image_path="/assets/images/atom_beta.png" alt="Figure 5 : Ce billet dans Atom 1.18 beta." caption="Figure 5 : Ce billet dans Atom 1.18 beta." %}

[^ide]: L'**I**ntegrated **D**evelopment **E**nvironment (Environnement de développement intégré) est un ensemble d'outils regroupés autour d'un éditeur de code et destinés à développer la productivité des programmeurs.
