---
layout: single
title: "Afficher des images en haute définition"
date: "2017-03-08 15:12:49 +0100"
categories: Photo
summary: Étape "traitement de l'image en grand format" dans le processus de création de photos *Gigapixels* consultables en ligne.
sidebar:
  nav: "pictures"
---
{% include toc %}  
Je vous propose aujourd'hui, toujours avec des outils libres et gratuits, d'afficher des images en haute définition sur votre site web. Vous pourrez en exploiter tous les détails en vous y déplaçant et en zoomant à volonté. Voyez ici un exemple de réalisation en ligne sur ce site.

## Les outils
### VIPS
[VIPS](http://www.vips.ecs.soton.ac.uk/index.php?title=VIPS) est un logiciel de traitement graphique en ligne de commande, extrêmement puissant. Nous ne ferons ici qu'en effleurer les possibilités. VIPS nous servira à découper l'image d'origine en un grand nombre de carreaux permettant des opérations de *zooming* et un affichage fluide.

* Si votre machine tourne sous *Linux*, *VIPS* fait à priori partie de votre distribution. Tapez `$ vips -v` dans un terminal pour le vérifier. Sinon, installez le package *VIPS* par la méthode habituelle.

* Sous *Windows* ou *Mac* : le site *VIPS* vous propose des téléchargements adaptés à votre système. Installez *VIPS* par ce moyen.

Il existe une interface graphique à *VIPS*, baptisée *NIPS2*. Je la trouve inutilement lourde et compliquée pour l'utilisation très simple que nous allons faire.

### OpenSeadragon
[OpenSeadragon](https://openseadragon.github.io/) (*l'hippocampe libre*) est un visualisateur d'images zoomables en haute définition. Il est *open source* et réalisé entièrement en Javascript. *OpenSeadragon* fonctionne aussi bien en local, sur votre clé USB par exemple, qu'en ligne sur un serveur distant. Comme il va être contenu dans une simple page web, vous pourrez l'utiliser à volonté sous *Linux*, *Windows* ou *Mac*.  

* Téléchargez l'archive disponible en première page du site.
* Créez un dossier de travail sur votre ordinateur. Appelez-le `zoom` pour simplifier.
* Décompactez-y votre archive

## Découpons l'image
Je suppose pour ce billet que vous disposez déjà d'une image en grand format. Que ce soit le *scan* d'une page de registres paroissiaux, un grand panorama[^1] que vous avez réalisé vous même, un tableau mis en ligne par un musée[^2] ou une photo issue d'une agence spatiale[^3].
Dans de nombreux cas, l'image *telle quelle* produite par un appareil photo d'une bonne définition sera suffisante. Je la nomme ici `grande-image.jpg`.

### Un espace de travail
Comme pour tout processus de création informatique, il est primordial de ranger ses fichiers selon une arborescence bien réfléchie.

* Allez dans votre dossier `zoom`
* Créez des sous-dossiers et organisez vos fichiers pour obtenir l'arborescence ci-contre.

---
[^1]: Nous verrons dans un prochain billet la *fabrication* de telles images.
[^2]: Parcourez par exemple les collections du [Metropolitan Museum of Art](http://www.metmuseum.org/art/collection) de New-York.
[^3]: Allez faire votre *marché* sur le site du téléscope spatial [Hubble](http://hubblesite.org/images/wallpaper).  
