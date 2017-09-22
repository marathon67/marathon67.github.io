---
title: "*WebSlides.js*, revisité"
date: "2017-09-21 15:00:20 +0200"
layout: single
categories: Twine, Photo
sidebar:
  nav: "twinery"
summary: "Améliorer *Webslides.js* par une extension bien utile."
header:
    overlay_color: rgba(75, 75, 0, 0.5)
---

{% include toc %}
>Si vous êtes adepte de **Powerpoint** ou apparenté, vous utilisez probablement l'apparition d'éléments successifs sur la même diapo. Lignes de texte, portions de graphiques... Pour produire ces effets, il manque à **WebSlides.js** une possibilité d'animation à l'intérieur d'une section.

# Merci, Tatsuya Iwamatsu

L'auteur original de **Webslides.js** ne semblant pas désireux d'ajouter cette fonctionnalité dans l'immédiat, un autre développeur, **Tatsuya Iwamatsu**, propose sur Github une extension à **Webslides**. Nommée [WebSlidesAnimation](https://github.com/iwamatsu0430/WebSlidesAnimation){:target="_blank"}, cette extension permet d'ajouter, à l'intérieur d'une section (diapositive), des effets d'animation par apparition/disparition ou mouvement des objets. Un peu de Javascript, un peu de CSS : **WebslideAnimation** est facile à mettre en œuvre et bien efficace. 

Pour vous en convaincre, j'ai modifié ma [démonstration de Webslides.js](https://www.bac-a-sable.eu/platypus/){:target="_blank"} en intégrant l'extension **WebslidesAnimation**. J'en est profité pour mettre à jour Webslides.js, qui en est maintenant à sa version **1.50**.

# Intégrer WebSlidesAnimation

La documentation de **WebslidesAnimation** est relativement claire et explicite. Pour résumer, il faut rajouter quelques lignes au code HTML de votre page, charger un fichier .css et un script .js. Vous pouvez télécharger l'ensemble du code de mon exemple depuis le [dépôt Github](https://github.com/marathon67/platypus){:target="_blank"} correspondant : 

### La feuille de style
Je ne modifie pas la feuille de style de Websildes, mais rajoute une nouvelle feuille, custom.css, dans laquelle je fais mes surcharges et mes ajouts. Ceci m'évite bien des pertes de temps au moment des mises à jour assez fréquentes de **Webslides**.

Voici ci-dessous le contenu actuel de ma feuille de style :

```
.animate-show {
    display: none !important;
  }
  .animate-show.animated {
    display: inherit !important;
  }
  
  .animate-show-visibility {
    opacity: 0 !important;
    visibility: hidden;
  }
  .animate-show-visibility.animated {
    opacity: 1 !important;
    visibility: visible;
  }
  
  .animate-hide {
    display: inherit !important;
  }
  .animate-hide.animated {
    display: none !important;
  }
  
  .animate-hide-visibility {
    opacity: 1 !important;
  }
  .animate-hide-visibility.animated {
    opacity: 0 !important;
  }
```
### Le fichier index.html

Chargement des feuilles de style :

```
   <link rel="stylesheet" type='text/css' media='all' href="static/css/webslides.css">
   <link rel="stylesheet" type='text/css' media='all' href="static/css/svg-icons.css">
   <link rel="stylesheet" type='text/css' media='all' href="static/css/custom.css">
```

Puis modification de la section 6, une photo plein écran avec une légende apparaissant au dessus après utilisation de la roulette de la souris ou de la touche [Flèche vers le bas] du clavier. 
Notez les deux lignes comprenant *data*. La première indique le nombre total d'étapes d'animation dans la section : `data-step-count=1` La seconde indique quel élément de la page doit apparaître : `animate-show" data-step=1`.

```
<section>
  <!-- Overlay/Opacity: [class*="bg-"] > .background.dark or .light -->
    <span data-step-count=1></span>
    <span class="background" style="background-image:url('static/images/ayers_rock.jpg')"></span>
    <div class="wrap">
      <div class="content-left bg-trans-dark fadeInUp animate-show" data-step=1>
        <h2><strong>Projet Ornithorynque</strong></h2>
        <p>Découvrez ici les travaux des élèves de CP de la classe de Madame Marckert ... après les congés d'été.</p>
      </div>
    </div> 
</section>
```
Et enfin, chargement du nouveau script .js, en fin de fichier HTML évidemment.

```
    <script src="static/js/webslides.js"></script>
    <script src="static/js/webslides-animation.js"></script>
    <script defer src="static/js/svg-icons.js"></script>
    <script type='text/javascript' src='https://cdn.knightlab.com/libs/soundcite/latest/js/soundcite.min.js'></script>
    <script>
      window.ws = new WebSlides();
      new WebSlidesAnimation(window.ws);
    </script>
  </body>
</html>
```


Et voilà, rien de bien compliqué. Il me reste à espérer que vous trouverez beaucoup de plaisir et/ou d'utilité à utiliser ce **Webslides.js** enrichi.