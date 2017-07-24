---
title: "*WebSlides*, un outil de storytelling"
date: "2017-07-07 15:00:20 +0200"
layout: single
categories: Twine
sidebar:
  nav: "twinery"
summary: "Raconter efficacement une histoire en ligne, sans forcémment la rendre interactive."
header:
    overlay_color: rgba(75, 75, 0, 0.5)
---

{% include toc %}
>Ma fille me demande : <span style="font-style:normal">"Aurais-tu une solution sympa pour mettre en ligne les dessins de mes élèves... un projet artistique sur les ornithorynques ?"</span> Et c'est en cherchant comment faire que j'ai trouvé **WebSlides** au détour de GitHub...

# Vu sur le Web

Vous avez certainement vu, dans les journaux en ligne, par exemple, de ces articles un peu longs qui intègrent de grandes images, des vidéos en pleine page et des textes fouillés, dans une présentation inspirée des sites "One pager" ? Attention, je ne vise pas ici à recréer les grosses machines que vous trouverez [sur Arte](http://www.arte.tv/sites/webdocs/){:target="_blank"} : superbes, spectulaires mais qui demandent des moyens financiers, techniques, humains... qui ne sont pas à la portée du premier venu. Et dépassent largement mes possibilités.

Je ne m'arrêterai pas non plus aux nombreuses réalisations de Réseau Canopé, comme la série [Raconte ta ville](https://www.reseau-canope.fr/raconte-ta-ville/webdoc/20162017.html){:target="_blank"}. Il s'agit là de webdocumentaires réalisés par des classes avec la solution [Klynt](http://www.klynt.net/fr/){:target="_blank"}. Klynt est un outil superbe, très utilisé par les grands médias, et suffisament facile à prendre en main pour travailler avec des élèves. Il a néanmoins l'inconvénient d'un prix non négligeable...

Ce que je recherche, c'est une présentation simple et gratuite, pour mettre en ligne une ou deux interviews de façon plaisante et efficace. Ou un conte illustré. Sans tomber dans ces présentations de site à l'ancienne, avec une malheureuse vidéo en petit format qui se bat en duel avec trois bouts de texte. Quand ce n'est pas avec des bannières de pub, toutes choses que je supporte de plus en plus difficilement.  

Il y a quelques années, pour réaliser un [roman-photo en ligne](http://formation.crdp-strasbourg.fr/webdoc/roman_photo/haute_bruche/s_entendre/){:target="_blank"} avec des élèves de lycée, j'avais découvert [JDocumentary](http://blog.evolya.fr/labo/fr/jdocumentary-v2/){:target="_blank"}. Malheureusement, cet outil n'est plus maintenu par son auteur et utilise des technologies obsolètes, comme le *plugin Flash*.

# WebSlides, un framework de présentation
D'où ma satifaction d'avoir découvert [WebSlides](https://webslides.tv){:target="_blank"}. Cet outil libre, disponible sur [Github](https://github.com/webslides/webslides){:target="_blank"}, vous permettra de réaliser sans grande difficulté des présentations /sites /récits superbes. Faites directement un tour du côté des [démos](https://webslides.tv/demos/){:target="_blank"} pour en voir tous le potentiel... J'ai été impressionné par la qualité des résultats.

Évidemment, ce n'est pas vraiment un outil destiné à *Madame Michu*... Il s'agit d'un *framework* **CSS** + **Javascript** et il nous faudra coder notre récit à la main. Utilisez pour ce faire un IDE *light*, comme **Sublime Text**, **Atom** ou **Visual Code Studio**.

J'apprécie beaucoup le compromis entre les nombreuses possibilités offertes d'une part, et la cohérence des présentations graphiques plutôt simplifiées, d'autre part. L'auteur a su faire des choix très efficaces.  
Vous pourrez faire défiler vos récits, au choix, horizontalement ou verticalement, par clic, scroll de la souris, touches `Fléches` ou `Espace` du clavier. **WebSlides** fait la part belle aux éléments graphiques de grand format, comme des vidéos ou des photos plein écran.  
Notez l'apparition des éléments de navigation au survol par la souris du haut ou du bas de page.  

Deux ou trois petites choses me gênent toutefois avec **Webslides**, malgré ses indéniables qualités.
D'abord la présentation du code sous forme d'un interminable fichier HTML. J'aimerais bien quelque chose de plus modulaire, avec un fichier par section/page par exemple.  Chacun des écrans correspond dans le code à une balise `<section> ... </section>`. Voyez l'exemple ci-dessous, présentant une page avec une photo couvrant toute la partie gauche de l'écran et le texte correspondant sur la droite :

```
<section class="fullscreen bg-apple text-apple text-context">   <!-- slide 06 -->
    <div class="card-50">      
      <div class="flex-content">
        <h2>À suivre !</h2>
        <p>Le site <em>Platypus</em> est un chantier en cours.</p>
        <p class="text-intro">Retenez bien notre adresse, notez-là dans vos favoris et ne manquez pas d'y revenir au mois de septembre.</p>
        <h3 class="anime zoomIn">https://www.bac-a-sable.eu/platypus</h3>
      </div>
      <!-- end .flex-content-->
      <figure>
        <img src="static/images/bushwalking.jpg" alt="Áqaba, Jordan">
        <figcaption>
          <a href="https://unsplash.com/@dburka" title="Daniel Burka">
            <svg class="fa-camera">
              <use xlink:href="#fa-camera"></use>
            </svg>
            Daniel Burka (Unsplash)
          </a>
        </figcaption>
      </figure>
    </div>
    <!-- end .card-50-->
</section>
```

Il me manque aussi la possibilité de faire apparaître un texte / un élément de page seulement au bout d'un temps donné ou après un clic de souris / un appui sur la touche `Espace`. Pour avoir le temps d'admirer en détail une photo plein écran, avant d'en découvrir la légende. 

Et enfin la documentation est remplacée par les nombreux fichiers de démo. Mais trouver dans les fichiers d'exemple (interminables, comme dit plus haut) une syntaxe précise est un peu galère.

Parmi les points positifs, le projet, disponible sur Github, est régulièrement maintenant et amélioré. Et son auteur, **José Luis Antúnez** répond rapidement aux éventuelles questions posées.

De mon côté, je travaille à la mise en place d'un thème **Jekyll** basé sur **WebSlides**, afin de rendre la création des présentation un peu plus efficace. Au cas où les ornithorynques se présenteraient en troupeaux. Je vous en reparlerais ici, pour autant que le résultat soit satisfaisant.

# WebSlides, pour quoi faire ?

Je compte bien utiliser cet outil de façon quasi systématique pour des récits longs. Un peu en concurrence avec [Twine](https://twinery.org){:target="_blank"}, quand il n'y a pas besoin d'interactivité. Idem pour la présentation de portfolios photo, où **WebSlides** remplacera efficacement les galeries classiques.
**WebSlides** fera également merveille pour des reportages et des interviews mêlant photos, vidéo et fichiers sonores.   

Je mettrais à contribution pour ces reportages [SoundCite](http://soundcite.knightlab.com/){:target="_blank"}. Cet outil fourni par **Knight Lab**, comme le **TimeLine.js** bien connu, permet d'insérer un fichier son directement et harmonieusement dans votre texte de présentation, sans le très agaçant bouton `Cliquez pour écouter`. **SoundCite** se marie vraiment très bien avec **WebSlides**.

Prenez le temps de découvrir WebSlides et ne manquez pas de me faire part de vos impressions en commentaires...