---
title: "Twine : quel format choisir ?"
date: '2017-04-24 12:25:30 +0200'
layout: single
categories: Twine
sidebar:
  nav: twinery
summary: Sugarcube ou Harlowe ? Vous avez le choix...
header:
  overlay_color: 'rgba(75, 75, 0, 0.5)'
---

{% include toc %}

> Parmi les trois formats d'histoires proposés dans Twine, je n'utilise plus guère que **Sugarcube**. Découvrez pourquoi dans la suite de ce billet.

Prêtez attention au menu principal de Twine, dans la colonne de droite, vous trouvez un item marqué **Formats**.

{% include figure image_path="/assets/images/twine-formats01.jpg" alt="Figure 1 : sélectionner les formats" caption="Figure 1 : sélectionner les formats." %}

Voyez sur la **figure 1** ci-dessus cet item marqué de rouge. Un clic fera apparaître une boîte de dialogue assez complexe : la boîte de paramétrage des formats.

{% include figure image_path="/assets/images/twine-formats02.jpg" alt="Figure 2 : boîte de dialogue des formats" caption="Figure 2 : boîte de dialogue des formats." %}

1. Onglets de sélection : ici, les formats d'histoire.
2. Étoile de format par défaut : cliquez dessus pour choisir le format attribué automatiquement aux nouvelles histoires.
3. Une première version de Sugarcube (1.0.34) livrée avec ma vieille version de Twine 2.0.11.
4. Une seconde version de Sugarcube (2.15.0) mise à jour manuellement.
5. Étoile de format par défaut : elle est bleue car j'ai sélectionné Sugarcube 2.15.0 comme format par défaut.
6. Poubelle : il est possible de désinstaller des formats ajoutés manuellement.
{: .notice}

# Histoire ... et correction

Twine utilise deux types différents de formats, qui bénéficient chacun d'un onglet séparé dans la boîte de dialogue. Il s'agit des formats d'histoire et des formats de correction.

Les **formats d'histoire** sont utilisés pour créer un récit dans Twine. Ce sont eux qui sont _responsable_ du type de programmation utilisée, de l'aspect des commandes, de l'interface utilisée pendant le jeu. Twine est livrée d'origine avec trois formats d'histoire différents : **Harlowe**, **Snowman** et **Sugarcube**. Ces formats d'histoire sont habituellement mis à jour plus rapidement que le logiciel Twine lui-même, mais il est très simple d'importer de nouveaux formats ou des mises à jour.

Les formats de correction permettent de visionner facilement l'ensemble d'une histoire, en la présentant sous forme textuelle, sans les _post_it_ de l'interface auteur. **Paperthin** est le format de correction livré par défaut avec Twine. Très peu de fonctionnalités : toute l'histoire d'un seul tenant, les passages séparés par une ligne pointillée, leurs titres en gras.

{% include figure image_path="/assets/images/twine-formats06.jpg" alt="Figure 3 : une histoire vue dans Paperthin" caption="Figure 3 : une histoire vue dans Paperthin." %}

De plus, **Paperthin** est un format _en lecture seulement_ : il n'est pas possible d'y effectuer des modifications au texte de votre histoire. En cas de faute d'orthographe, par exemple, la correction devra se faire obligatoirement dans les *post-it" de l'interface de saisie.

## Illume, un format à essayer

Michael McCollum nous [propose une alternative](http://www.maximumverbosity.net/twine/Illume/){: target="_blank"} aux possibilités très limitées de **Paperthin** : le format de correction **Illume**.

{% include figure image_path="/assets/images/twine-formats07.jpg" alt="Figure 4 : une histoire vue dans Illume" caption="Figure 4 : une histoire vue dans Illume." %}

Il offre des fonctions de statistiques, permet de lister les modifications effectuées, d'exporter le travail vers différents formats. Mais toujours pas d'éditer effectivement le texte de l'histoire avant de le ré-injecter dans Twine. Dommage... comme le fait que son interface soit exclusivement en anglais. Pour l'installation de **Illume**, voyez plus bas la section [Mise à jour](#mise-à-jour).

# Mise à jour

Pour mettre à jour une version de **Harlowe** ou **Sugarcube**,

* Allez sur leurs sites respectifs et télécharger l' archive *.zip correspondante
* Décompactez-là à l'endroit de votre choix. Pour ma part, je copie les formats dans un sous-répertoire de mon dossier Twine. Sous Linux, ceci me donnera `/home/pierre/Twine_2.0.11/SugarCube-2/`.

A partir de là, pour installer **Illume**, la manœuvre sera identique :

* Ouvrez la boîte de dialogue des formats comme indiqué en figure 1
* Sélectionnez l'onglet *Ajouter un format*
* Dans la boîte de dialogue ci-dessus, entrez l'adresse du format. Selon les cas, ce sera une adresse de type web (`http://www.maximumverbosity.net/twine/Illume/format.js` pour Illume) ou de type fichier pour Sugarcube (`/home/pierre/Twine_2.0.11/SugarCube-2/format.js` sur mon ordinateur). Dans tous les cas, c'est l'adresse du fichier javascript `format.js` qu'il faut entrer.
* Cliquez sur le bouton vert `Ajouter`.

Par suite de bugs récurrents, il n'est pas possible de mettre à jour ou d'installer des formats dans les versions 2.1.x de Twine. Voyez [cet article](/twine/twine-quelle-version-choisir/) pour le choix d'une version de Twine.
{: .notice--danger}

# Harlowe

**Harlowe** est une création de Leon Arnott. Sa [documentation](https://twine2.neocities.org/2.html){:target="_blank"} est disponible sur le site de l'auteur. Voyez ici _Le loup et l'agneau_ un [example][9f404067]{: target="_blank"} d'histoire réalisée avec le format d'histoire **Harlowe**.

Ce format propose par défaut une interface claire, simple et agréable. Il convient parfaitement aux nouveaux utilisateurs qui ne veulent pas utiliser de façon très approfondie les possibilités de codage offertes dans Twine. Les débutants auront tout intérêt à choisir **Harlowe** pour commencer leur exploration de Twine.

```
{
(set: $photo='<img src="./images/'+ (passage:)'s name + '.jpg" />')
(set: $son_auto='<audio src="./son_auto/'+ (passage:)'s name + '.mp3" autoplay />')
}
```
<figcaption>Figure 5 : un example de code dans Harlowe</figcaption>


**Harlowe** est le format d'histoire par défaut dans les versions 2 de Twine.
{: .notice--danger}

# Sugarcube
**Sugarcube** est une création de Thomas Michael Edwards. Sa [documentation](http://www.motoslave.net/sugarcube/2/){:target="_blank"} est particulièrement complète et compréhensible (bien qu'en anglais...). De plus, l'auteur est très actif sur le [forum Twine](http://twinery.org/forum/){:target="_blank"} et fait habituellement des réponses très complètes, assorties d'exemple de code, aux questions qui sont posées. Surveillez le pseudo _TheMadExile_.

Par défaut, **Sugarcube** se présente avec une interface sur fond noir que j'apprécie peu. L'auteur fournit néamoins une feuille de style permettant d'afficher l'histoire de façon plus classique. Pour plus de détails, voyez [cet article][aa03e34e].

```
<<set $online_medias_url to "https://www.bac-a-sable.eu/mini-monde/medias/">>
<<initInv>>
<<set $son_nuit to $online_medias_url+"start.mp3">>
<<set $son_maison to $online_medias_url+"maison.mp3">>
```
<figcaption>Figure 6 : un example de code dans Sugarcube</figcaption>

**Sugarcube** facilite le développement d'une interface personnalisée sans trop de difficultés.
{: .notice--danger}

# Snowman
**Snowmann** est conçu et maintenu par le créateur de Twine lui-même, Chris Klimas. Dans le forum Twine, vous le rencontrerez sous le pseudo de *Klembot*. Il définit son format d'histoire comme *un format minimaliste, dessiné pour des utilisateurs maîtrisant Javascript et CSS*.
Quasi inutilisable sans un important travail de programmation, mais ouvert à toutes les extensions et personnalisations. Si vous fréquentez le forum, vous verrez rapdement que **Snowman** est, de loin, le format le moins populaire. Vous trouverez (un tout petit peu) plus d'infos dans le [dépôt Bitbucket](https://bitbucket.org/klembot/snowman-1.4){: target="_blank"} de Chris.

Pour quelqu'un qui débute dans la rédaction d'histoires sous Twine, **Snowman** n'est pas le choix le plus pertinent.
{: .notice--danger}

# Pourquoi plutôt Sugarcube ?

**Sugarcube** est aujourd'hui mon format d'histoire par défaut, bien que j'ai commencé par écrire des histoires simples sous **Harlowe**. Sa plus grande richesse en matière d'outils simples pour enrichir programmatiquement une histoire a fini par me séduire. Avec **Harlowe**, vous finirez presque certainement par vous trouver un peu à l'étroit dans le jeu des fonctions et commandes proposées par défaut. Certes, il est toujours possible de créer de nouvelles fonctionnalités à grands coups de Javascript. Mais **Sugarcube** offre nativement la plupart des outils dont j'ai besoin. J'y ai apprécié tout particulièrement :

* l'interface de navigation latérale, facilement personnalisable
* la gestion fine des ambiances sonores

### En résumé
* Vous êtes débutant : **Harlowe**
* Vous voulez pimenter vos histoires d'un peu de programmation : **Sugarcube**
* Vous êtes un développeur chevronné : **Snowman**
{: .notice--danger}


[9f404067]: https://www.bac-a-sable.eu/agneau/ "Le loup et l'agneau"
[aa03e34e]: /twine/ready-made-css/ "Ready-made CSS"
