---
layout: single
title: "Afficher des images en haute définition"
date: "2017-03-08 15:12:49 +0100"
categories: Photo
summary: Étape "traitement de l'image en grand format" dans le processus de création de photos *Gigapixels* consultables en ligne.
sidebar:
  nav: "pictures"
---

Je vous propose aujourd'hui, toujours avec des outils libres et gratuits, d'afficher des images en haute définition sur votre site web. Vous pourrez en exploiter tous les détails en vous y déplaçant et en zoomant à volonté. Voyez ici un exemple de réalisation en ligne sur ce site.

## Les outils
### VIPS
[VIPS](http://www.vips.ecs.soton.ac.uk/index.php?title=VIPS) est un logiciel de traitement graphique en ligne de commande, extrêmement puissant. Nous ne ferons ici qu'en effleurer les possibilités. VIPS nous servira à découper l'image d'origine en un grand nombre de carreaux permettant des opérations de *zooming* et un affichage fluide.

* Si votre machine tourne sous *Linux*, *VIPS* fait à priori partie de votre distribution. Tapez `$ vips -v` dans un terminal pour le vérifier. Sinon, installez le package *VIPS* par la méthode habituelle.

* Sous *Windows* ou *Mac* : le site *VIPS* vous propose des téléchargements adaptés à votre système.

Il existe une interface graphique à *VIPS*, baptisée *NIPS2*. Je la trouve inutilement lourde et compliquée pour l'utilisation très simple que nous allons faire.

## L'image d'origine
Je suppose pour ce billet que vous disposez déjà d'une image en grand format. Que ce soit le *scan* d'une page de registres paroissiaux, un grand panorama[^1] que vous avez réalisé vous même, un tableau mis en ligne par un musée[^2] ou une photo issue d'une agence spatiale[^3].
Dans de nombreux cas, l'image *telle quelle* produite par un appareil photo d'une bonne définition sera suffisante.


---
[^1]: Nous verrons dans un prochain billet la *fabrication* de telles images.
[^2]: Parcourez par exemple les collections du [Metropolitan Museum of Art](http://www.metmuseum.org/art/collection) de New-York.
[^3]: Allez faire votre *marché* sur le site du téléscope spatial [Hubble](http://hubblesite.org/images/wallpaper).  
