---
title: "Twine : nouvelles versions"
date: "2017-05-11 10:04:05 +0200"
layout: single
categories: Twine
sidebar:
  nav: "twinery"
summary: "Sortie pendant le week-end du 1er mai 2017 de la version 2.1.3 de Twine."
header:
    overlay_color: rgba(75, 75, 0, 0.5)
---

{% include toc %}

> Depuis mon [article]({{ site.baseurl }}{% post_url 2017-03-24-twine--quelle-version-choisir- %}) sur le choix d'une version de **Twine**, pas mal de nouveautés. Et des progrès, autant pour le logiciel **Twine** que pour ses principaux formats d'histoire, **Harlowe** et **Sugarcube**.

## Twine 2.1.3

Depuis le début de la série 2.1 de Twine, je déplorais une série de bugs sévères m'obligeant à en rester à la bonne vieille et éprouvée version 2.0.11. La version 2.1.3 lève (presque) entièrement la malédiction.

Les améliorations apportées ici sont surtout visibles au niveau de l'ergonomie. L'interface graphique a été entièrement repris, pour une bien meilleure lisibilité de la *carte des passages*. Un plus notable dès que votre histoire commence à s'étoffer quelque peu.

Quand vous lancez votre histoire dans **Twine**, un clic droit vous permet maintenant d'inspecter l'élément de votre choix avec les outils de développement de **Chrome**. Bien pratique pour effectuer rapidement des modifications de CSS.

* [Notes de version](https://twinery.org/wiki/twine2:release_notes){:target="_blank"}
* [Téléchargements](https://twinery.org/){:target="_blank"}
* [Documentation complète](https://twinery.org/wiki/twine2:guide){:target="_blank"}
{: .notice}

La version 2.1.3 intègre les formats d'histoire **Harlowe** 2.0.1 et **Sugarcube** 2.18.0. Voyez ci-dessous leurs présentations plus détaillées.

### Une habitude à prendre
Dans **Twine**, la syntaxe suivante est utilisée pour faire un lien entre le passage que vous êtes en train d'éditer et un autre passage :
```
 [[Mon passage|passage]]
```
Si le nouveau passage n'existe pas, **Twine** le crée automatiqument, du moins en théorie. Un petit bug, facile à contourner, produit parfois la situation illustrée dans la figure 2 ci-dessous.

{% include figure image_path="/assets/images/twine-bug01.jpg" alt="Figure 1 : éditeur de passages." caption="Figure 1 : éditeur de passages." %}

* Si je ferme le passage en train d'être édité en cliquant n'importe où en dehors du cadre d'édition : pas de nouveau passage créé automatiquement, juste la croix rouge d'erreur de lien...
* Si je ferme proprement le passage en train d'être édité en cliquant sur la petite croix noire (fléchée en figure 1), tout se passe normalement.

Prenons donc, en attendant la correction de ce bug minime, l'habitude de fermer *proprement* l'éditeur.

{% include figure class="half" image_path="/assets/images/twine-bug02.jpg" alt="Figure 2 : J'ai mal fermé l'éditeur." caption="Figure 2 : J'ai mal fermé l'éditeur." %}

Pour mettre à jour les formats d'histoire, voir la section correspondante dans mon article  [Twine : quel format choisir]({{ site.baseurl }}{% post_url 2017-04-24-quelformatchoisir %}).
{: .notice--danger}

## Harlowe 2.0.1

La version 2 de **Harlowe** apporte de nombreuses améliorations en ce qui concerne la mise en page et la programmation. Elle refait ainsi une partie de son retard sur **Sugarcube**, qui est jusqu'à présent mon format favori... Il va falloir que je fasse de nouveaux essais.
Parmi toutes ces nouveautés, j'ai entre autres noté un nouveau marquage permettant de disposer les textes en colonne dans un passage. Et une série d'ajouts, tant dans le marquage que les macros, pour gérer l'apparition et la disparition de liens dans les passages.

* [Notes de version](https://bitbucket.org/_L_/harlowe){:target="_blank"}
* [Téléchargements](https://bitbucket.org/_L_/harlowe/downloads/){:target="_blank"}
* [Documentation complète](https://twine2.neocities.org/){:target="_blank"}
{: .notice}

### Revenir à un thème clair
Le thème de base dans **Harlowe** est désormais sombre, texte blanc sur fond noir, comme dans **Sugarcube**, alors qu'il proposait des caractères noirs sur fond blanc dans les précédentes versions.
L'ancien thème clair peut être restauré en insérant le code suivant dans un passage portant le tag `header`.

```
(enchant: ?page, (text-colour:black)+(background:white))
```

## Sugarcube 2.18.0

**Sugarcube** se développe à un rythme nettement plus rapide que son rival **Harlowe**. Huit mises à jour se sont déjà succédées depuis le début de l'année 2017 ! Vous y trouverez une série d'ajouts fort intéressants dans les dernières versions. Les évolutions récentes les plus importantes se situent probablement dans les possibilités offertes par l'auteur de modifier (assez) facilement l'interface utilisateur.(API *UiBar* et special passage *StoryInterface*).

J'ai également appécié l'introduction de `Config.navigation.override` dont vous voyez ci-dessous un exemple d'utilisation tiré de mon [Mini-monde](https://www.bac-a-sable.eu/mini-monde/){:target="_blank"}.
En glissant dans le Javascript de votre aventure un *bout de code* équivalent, vous allez pouvoir surveiller dans l'ensemble des passages, une condition fixée à l'avance. Ici, à chaque lien vers un autre passage, je teste si le joueur a déjà rencontré tous les animaux. Auquel cas il a gagné et est automatiquement envoyé au passage `victoire`.
Pratique, et pas bien compliqué.

```
/*! Passage Override en cas de victoire */
Config.navigation.override = function (passageName) {
  if (State.variables.animaux == State.variables.max_animaux)
  {return "victoire";}
};
```

Si comme moi, vous n'appréciez pas la présentation blanc sur fond noir de **Sugarcube**, sachez que l'auteur a également mis à jour la feuille de style spécifique *Bleachit*, qui permet d'obtenir un **Sugarcube** clair. Voyez l'article [Feuilles de style ready-made pour Sugarcube]({{ site.baseurl }}{% post_url 2017-02-28-ready-made-css %}) pour plus de détails sur la façon de la télécharger et de l'utiliser.

* [Notes de version](http://www.motoslave.net/sugarcube/2/releases.php){:target="_blank"}
* [Documentation complète et téléchargements](http://www.motoslave.net/sugarcube/2/){:target="_blank"}
{: .notice}
