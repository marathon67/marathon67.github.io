---
layout: single
title: "Afficher des images en haute définition"
date: "2017-03-08 15:12:49 +0100"
categories: Photo
summary: Étape "traitement de l'image en grand format" dans le processus de création de photos *Gigapixels* consultables en ligne.
sidebar:
  nav: "pictures"
header:
      overlay_color: rgba(0, 70, 0, 0.5) # photo : rgba(0, 70, 0, 0.5), twine : rgba(75, 75, 0, 0.5), jekyll : rgba(0, 20, 120, 0.5), divers : rgba(0, 0, 70, 0.5)
---
{% include toc %}
Je vous propose aujourd'hui, toujours avec des outils libres et gratuits, d'afficher des images en haute définition sur votre site web. Vous pourrez en exploiter tous les détails en vous y déplaçant et en zoomant à volonté. Voyez ici un exemple de réalisation en ligne sur ce site.

## Les outils
### VIPS
[VIPS](http://www.vips.ecs.soton.ac.uk/index.php?title=VIPS) est un logiciel de traitement graphique en ligne de commande, extrêmement puissant. Nous ne ferons ici qu'en effleurer les possibilités. *VIPS* nous servira à découper l'image d'origine en un grand nombre de carreaux permettant des opérations de *zooming* et un affichage fluide.

* Si votre machine tourne sous *Linux*, *VIPS* fait à priori partie de votre distribution. Tapez `$ vips -v` dans un terminal pour le vérifier. Sinon, installez le package *VIPS* par la méthode habituelle.

* Sous *Windows* ou *Mac* : le site *VIPS* vous propose des téléchargements adaptés à votre système. Installez *VIPS* par ce moyen.

Il existe une interface graphique à *VIPS*, baptisée *NIPS2*. Je la trouve inutilement lourde et compliquée pour l'utilisation très simple que nous allons faire.

### OpenSeadragon
[OpenSeadragon](https://openseadragon.github.io/) (*l'hippocampe libre*) est un visualisateur d'images zoomables en haute définition. Il est *open source* et réalisé entièrement en Javascript. *OpenSeadragon* fonctionne aussi bien en local, sur votre clé USB par exemple, qu'en ligne sur un serveur distant. Comme il va être contenu dans une simple page web, vous pourrez l'utiliser à volonté sous *Linux*, *Windows* ou *Mac*.

* Téléchargez l'archive disponible en première page du site.
* Créez un dossier de travail sur votre ordinateur. Appelez-le `zoom` pour simplifier.
* Décompactez-y votre archive.

## Découpons l'image
Je suppose pour ce billet que vous disposez déjà d'une image en grand format. Que ce soit le *scan* d'une page de registres paroissiaux, un grand panorama[^1] que vous avez réalisé vous même, un tableau mis en ligne par un musée[^2] ou une photo issue d'une agence spatiale[^3].
Dans de nombreux cas, l'image *telle quelle* produite par un appareil photo d'une bonne définition sera suffisante. Pour notre démonstration, j'ai choisi une photo de la [Nébuleuse d'Orion](http://imgsrc.hubblesite.org/hvi/uploads/image_file/image_attachment/29604/ps16_16x20.jpg) (3,29 Mo) disponible sur le site du télescope spatial. Je la renomme `orion.jpg`.

Procédons au découpage proprement dit :

* ouvrez un terminal de commande
* entrez-y la ligne suivante : `vips dzsave orion.jpg orion`

![VIPS](/assets/images/vips01.jpg)

La capture ci-dessus vous montre à la fois le terminal et le résultat produit dans l'explorateur de fichiers :

* `orion.dzi` est un fichier de métadonnées permettant l'affichage de votre image
* `orion_files` est un dossier renfermant tous les carrés de l'image découpée
* les 13 sous-dossiers, contiennent des carrés d'image, regroupés par niveau de zoom

Pour compléter, je crée dans *The Gimp* une vignette en 256x256 pixels, que je nomme `orion_th.jpg`[^4].

### Un espace de travail
![VIPS](/assets/images/vips02.jpg){: .align-left}
Pour tout processus de création informatique, il est primordial de ranger ses fichiers selon une arborescence réfléchie.


Pour en obtenir une semblable à la mienne :

* Allez dans votre dossier `zoom`
* Créez un sous-dossier `scripts` et un sous-dossier `giga`
* Dans giga, copiez le fichier `openseadragon.min.js` et le dossier `images` tirés de l'archive d'*OpenSeadragon*.
* Déplacez dans giga le fichier `orion.dzi` et le dossier `orion_files`

## La page Web

Pour afficher notre nébuleuse, il ne nous manque plus une page HTML à visiter avec notre navigateur.

* Créez dans votre dossier zoom un nouveau fichier `index.html`
* Ouvrez-le dans votre éditeur de code favori[^5]
* Copiez-y le code ci-dessous (après avoir cliqué sur *View Raw*)
* Enregistrez
* Vous pouvez également télécharger ce fichier sous forme d'archive en cliquant sur *zoom_orion.html* en bas du cadre de code.

<script src="https://gist.github.com/marathon67/89c75a0a3ac52656b89b3f05424b3b3e.js"></script>


### Une pincée de css

Pour rendre les choses un peu plus élégantes, rajoutons une feuille de style.

* Créez dans votre dossier zoom un nouveau fichier `zoom.css`
* Ouvrez-le dans votre éditeur de code favori
* Copiez-y le code ci-dessous
* Enregistrez

<script src="https://gist.github.com/marathon67/9455c7f7702dae203394dc4d607f5520.js"></script>

## Et voilà !
Il vous reste maintenant à ouvrir `index.html` dans votre navigateur et vérifier que tout fonctionne. Voyez mon [exemple](https://www.bac-a-sable.eu/gigapics/) sur Github.
Évidemment il vous faudrait encore enrichir la feuille de style pour adapter le *look* d'*OpenSeadragon* à celui de votre site.
Je vous montre dans un tout prochain billet ce que cela donne intégré dans mon site *Jeckyll*.

[^1]: Nous verrons dans un prochain billet la *fabrication* de telles images.
[^2]: Parcourez par exemple les collections du [Metropolitan Museum of Art](http://www.metmuseum.org/art/collection) de New-York.
[^3]: Allez faire votre *marché* sur le site du téléscope spatial [Hubble](http://hubblesite.org/images/wallpaper).
[^4]: `_th` comme *thumbnail*, miniature en anglais.
[^5]: En ce qui me concerne, et depuis un bout de temps, c'est [Atom](https://atom.io/).
