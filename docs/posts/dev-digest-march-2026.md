---
date: 2026-04-07
category:
  - Veille
tag:
  - HTML
  - CSS
  - JS
---

# La veille du mois : Mars 2026

Ah mais vous êtes là vous ? Bah alors comment ils vont depuis le temps ?
Ça tombe bien, j'allais faire un tour des nouveautés dans le web, asseyez-vous, je vais vous montrer tout ça !

## Côté HTML

### Element Select personalisable

La dernière fois que j'en avais parlé, la feature n'était disponible que sur des versions relativement récentes de chromium, à savoir que Safari a sorti le support de son côté également en Technical Preview, il devrait donc être disponible dans la prochaine version majeure de Safari au plus tard, soit avec la sortie de la prochaine version de MacOS !

<style src="./driver-select.css"></style>

<select>
  <button>
    <selectedcontent></selectedcontent>
  </button>
  <option>
    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M12 4a9 9 0 0 1 5.656 16h-11.312a9 9 0 0 1 5.656 -16" /><path d="M20 9h-8.8a1 1 0 0 0 -.968 1.246c.507 2 1.596 3.418 3.268 4.254c2 1 4.333 1.5 7 1.5" /></svg>
    <span>- select -</span>
  </option>
  <option data-team="Aston Martin" data-color="#229971" value="Alonso">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/alonso.png" alt="Alonso">
    <span>Alonso</span>
  </option>
  <option data-team="Aston Martin" data-color="#229971" value="Stroll">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/lance.png" alt="Stroll">
    <span>Stroll</span>
  </option>
  <option data-team="Williams" data-color="#1868db" value="Albon">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/albon.png" alt="Albon">
    <span>Albon</span>
  </option>
  <option data-team="Williams" data-color="#1868db" value="Sainz">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/sainz.png" alt="Sainz">
    <span>Sainz</span>
  </option>
  <option data-team="Audi" data-color="#f50537" value="Bortoleto">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/bortoleto.png" alt="Bortoleto">
    <span>Bortoleto</span>
  </option>
  <option data-team="Audi" data-color="#f50537" value="Hulkenberg">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/hulkenberg.png" alt="Hulkenberg">
    <span>Hülkenberg</span>
  </option>
  <option data-team="Alpine" data-color="#00a1e8" value="Gasly">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/gasly.png" alt="Gasly">
    <span>Gasly</span>
  </option>
  <option data-team="Alpine" data-color="#00a1e8" value="Colapinto">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/colapinto.png" alt="Colapinto">
    <span>Colapinto</span>
  </option>
  <option data-team="Cadillac" data-color="#909090" value="Pérez">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/erez.png" alt="Pérez">
    <span>Pérez</span>
  </option>
  <option data-team="Cadillac" data-color="#909090" value="Bottas">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/bottas.png" alt="Bottas">
    <span>Bottas</span>
  </option>
  <option data-team="McLaren" data-color="#f47600" value="Norris">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/norris.png" alt="Norris">
    <span>Norris</span>
  </option>
  <option data-team="McLaren" data-color="#f47600" value="Piastri">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/piastri.png" alt="Piastri">
    <span>Piastri</span>
  </option>
  <option data-team="Mercedes" data-color="#00d7b6" value="Antonelli">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/anotonelli.png" alt="Antonelli">
    <span>Antonelli</span>
  </option>
  <option data-team="Mercedes" data-color="#00d7b6" value="Russell">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/russell.png" alt="Russell">
    <span>Russell</span>
  </option>
  <option data-team="Red Bull" data-color="#4781d7" value="Hadjar">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/hadjar.png" alt="Hadjar">
    <span>Hadjar</span>
  </option>
  <option data-team="Red Bull" data-color="#4781d7" value="Verstappen">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/verstappen.png" alt="Verstappen">
    <span>Verstappen</span>
  </option>
  <option data-team="Ferrari" data-color="#ed1131" value="Leclerc">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/leclerc.png" alt="Leclerc">
    <span>Leclerc</span>
  </option>
  <option data-team="Ferrari" data-color="#ed1131" value="Hamilton">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/hamilton.png" alt="Hamilton">
    <span>Hamilton</span>
  </option>
  <option data-team="Haas" data-color="rgb(156, 159, 162)" value="Ocon">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/ocon.png" alt="Ocon">
    <span>Ocon</span>
  </option>
  <option data-team="Haas" data-color="rgb(156, 159, 162)" value="Bearman">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/bearman.png" alt="Bearman">
    <span>Bearman</span>
  </option>
  <option data-team="Racing Bulls" data-color="#6c98ff" value="Lindblad">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/lindblad.png" alt="Lindblad">
    <span>Lindblad</span>
  </option>
  <option data-team="Racing Bulls" data-color="#6c98ff" value="Lawson">
    <img src="https://raw.githubusercontent.com/cbolson/assets/refs/heads/main/codepen/f1/2026/lawson.png" alt="Lawson">
    <span>Lawson</span>
  </option>
</select>

<style>
  .ciu_embed {
    width: 100%;
    border: none;
  }
</style>
<iframe class="ciu_embed" src="https://caniuse.pengzhanbo.cn/customizable-select#past=2&future=3&theme=light" height="483px" scrolling="no"></iframe>

## Côté CSS

### Animation au scroll

<style>
@keyframes grow-bar {
  from {
    width: 0%;
  }
  to {
    width: 100%;
  }
}

body:has(#la-veille-du-mois-mars-2026) .vp-navbar::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  height: 2px;
  background: var(--vp-c-accent);

  animation: grow-bar linear both;
  animation-timeline: scroll(root);
}
</style>

Je vais attirer votre attention vers le haut de la page, j'y ai ajouté une barre de progression pour cet article, sachez qu'il n'y a aucun javascript derrière, voici le contenu de la balise `<style>` de la page:

```css
@keyframes grow-bar {
  from {
    width: 0%;
  }
  to {
    width: 100%;
  }
}

body:has(#la-veille-du-mois-mars-2026) .vp-navbar::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  height: 2px;
  background: var(--vp-c-accent);

  animation: grow-bar linear both;
  animation-timeline: scroll(root);
}
```

Dans ce cas, on attache une animation à la barre qui change sa taille, et on précise que la position dans l'animation est dictée par la progression du scroll actuel dans la page !

Et si vous vous posez la question, oui, on peut aussi faire une animation quand un élément entre dans la viewport !

<style>
.fancy-animation {
  color: grey;
  font-style: italic;
  
  animation: card-in cubic-bezier(0.22, 1, 0.36, 1) both;
  animation-timeline: view();
  animation-range: entry 5% entry 500%;
}

@keyframes card-in {
  from {
    opacity: 0;
    scale: 0;
    filter: blur(4px);
  }
  to {
    opacity: 1;
    scale: 1;
    filter: blur(0px);
  }
}
</style>

<p class="fancy-animation">
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
</p>
<p class="fancy-animation">
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
</p>
<p class="fancy-animation">
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<p class="fancy-animation">
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</p>

```css
.fancy-animation {
  color: grey;
  font-style: italic;
  animation: card-in cubic-bezier(0.22, 1, 0.36, 1) both;
  animation-timeline: view();
  animation-range: entry 5% entry 500%;
}

@keyframes card-in {
  from {
    opacity: 0;
    scale: 0;
    filter: blur(4px);
  }
  to {
    opacity: 1;
    scale: 1;
    filter: blur(0px);
  }
}
```

Ici, l'animation commence quand 5% de l'élément est visible, et se termine quand 500% est visible (ce qui permet de faire durer l'animation plus longtemps pour l'exemple, idéalement, l'animation est terminée avant que l'élément (une card par exemple) soit pleinement visible)

Tous les navigateurs supportent la feature... sauf Firefox, ou c'est encore derrière un flag.

### Grid lanes (Autrefois Masonry Layout)

Mise en scène: il est 10h, un designer vous envoie un design, vous l'ouvrez et vous voyez ça:

![Un example de layout "Masonry"](/assets/posts/dev-digest-march-2026/grid-lanes.png)

Une fois passée la crisse d'angoisse, comment faites-vous ?

Aujourd'hui, la solution est d'utiliser une librairie comme [masonry-layout](https://www.npmjs.com/package/masonry-layout) pour le faire, et n'essayez pas de faire quelque chose de dynamique, puisque chaque chargement d'image, changement de taille ou quelconque mise à jour du DOM demande un nouvel appel à la fonction `layout()` de la librairie !

...Ou alors, [vous bossez sur un site qui ne doit marcher que sur Safari](https://webkit.org/blog/17660/introducing-css-grid-lanes/)

```html
<main class="container">
  <figure><img src="photo-1.jpg"></figure>
  <figure><img src="photo-2.jpg"></figure>
  <figure><img src="photo-3.jpg"></figure>
  <!-- etc -->
</main>
```

```css
.container {
  display: grid-lanes;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 16px;
}
```

Et le pire c'est qu'ils friment avec leur tech !

![Un example de layout "Masonry" plus complexe](/assets/posts/dev-digest-march-2026/grid-lanes-2.png)

```css
main {
  display: grid-lanes;
  grid-template-columns: repeat(auto-fill, minmax(20ch, 1fr));
  gap: 2lh;
}
article { 
  grid-column: span 1; 
}
@media (1250px < width) {
  article:nth-child(1) { 
    grid-column: span 4;             
  }
  article:nth-child(2), article:nth-child(3), article:nth-child(4), article:nth-child(5), article:nth-child(6), article:nth-child(7), article:nth-child(8) { 
    grid-column: span 2; 
  }
}
```

Alors on peut être rassuré, si votre navigateur est à jour, vous pouvez activer le feature flag "experimental web features" (le nom diffère selon les navigateurs, mais globalement c'est plus ou moins ça), et [la demo devrait être fonctionnelle pour vous aussi](https://webkit.org/demos/grid3/newspaper/), ça arrive bientôt !

<iframe class="ciu_embed" src="https://caniuse.pengzhanbo.cn/css-grid-lanes#past=2&future=3&theme=light" height="447px" scrolling="no"></iframe>

### Field Sizing

Tiens, écris ici pour voir

<style>
textarea.example {
  field-sizing: content;
  min-width: 50px;
  max-width: 150px;
  resize: none;
}
</style>

<textarea id="example" name="example" class="example"></textarea>

T'as vu, ça change de taille selon le texte, cool non ?

Une ligne de CSS. `field-sizing: content;`.

J'ai dû coder ça sur un projet angular, c'est une directive de 50 lignes qui clone la textarea avec une nouvelle taille, et supprime l'ancienne à chaque nouvel input.

C'est dispo sur chrome depuis 2024, safari depuis novembre 2025.

C'est pas sur Firefox.

Au revoir.

### if()

Un dernier truc un peu moins récent, mais quand même notable;
Je l'avais mentionné à la toute fin du dernier article, et c'était pas une blague, ça va faire un an le mois prochain qu'on peut faire ça dans les navigateurs chromium

```css
.button {
  background: if(style(--variant: primary): blue; else: gray);
  border: none;
}
```

```html
<button class="button" style="--variant: primary">Hello !</button>
<button class="button">World !</button>
```

<style>
.button {
  background: if(style(--variant: primary): blue; else: gray);
  border: none;
}
</style>

<button class="button" style="--variant: primary">Hello !</button>
<button class="button">World !</button>

<iframe class="ciu_embed" src="https://caniuse.pengzhanbo.cn/css-if#past=2&future=3&theme=light" height="448px" scrolling="no"></iframe>

Et puis c'est quoi la suite, des fonctions en CS- oh c'est quoi ce lien ?

[https://drafts.csswg.org/css-mixins](https://drafts.csswg.org/css-mixins)

![Un example de fonctions en CSS](/assets/posts/dev-digest-march-2026/css-functions.png "...j'y reviendrais une autre fois")

## Côté Javascript

### View Transitions

Pour commencer, voici un exemple concret de l'API view transition:

<iframe
  height="500"
  style="width: 100%;"
  scrolling="no"
  title="View transition API demo"
  src="https://codepen.io/editor/PavelLaptev/embed/019cf895-57da-782e-b966-e4f3865a0c31?default-tab=js%2Cresult"
  frameborder="no"
  loading="lazy"
  allowtransparency="true">
</iframe>

L'API View Transitions nous permet de marquer les éléments du DOM en cours de changement via un appel Javascript à `document.startViewTransition`, et de les animer via les règles CSS `::view-transition-old` et `::view-transition-new`

Point bonus, on peut aussi marquer les éléments côté CSS via la règle `view-transition-name`, et laisser le navigateur animer le passage d'un endroit à un autre par lui même !

Voici un autre exemple sur une table on ne peut plus classique, essayez de cliquer sur les headers "Release Year" et "Rating" pour réordonner les lignes !

<iframe
  height="500"
  style="width: 100%;"
  scrolling="no"
  title="Sortable Table With View Transitions"
  src="https://codepen.io/OuterVale/embed/gbPaYxe?default-tab=result&editable=true"
  frameborder="no"
  loading="lazy"
  allowtransparency="true">
</iframe>

Vous pouvez aussi jouer avec le code CSS, vous remarquerez que la seule ligne de CSS qui permet d'avoir cette animation est la ligne `view-transition-name: match-element;` !

Si vous voulez un exemple encore plus impressionnant : [voici une liste de playlist avec une animation à l'ouverture gérée automatiquement par le navigateur !](https://live-transitions.pages.dev/)

![Extrait du code CSS pour l'example partagé ci-dessus =300x](/assets/posts/dev-digest-march-2026/code-view-transition-name.png 'Voici un extrait du code source pour les animations, on nomme les items pour indiquer au navigateur quelles elements sont lié avant et après la transition !')

En l'état, avec les animations au scroll, nous avons de quoi passer outre des librairies comme GSAP pour nos animations sur le web, la seule feature qui rendrait cette API encore plus incroyable, ça serait de pouvoir faire des animations d'une page HTML à une autre...

[Ça tombe bien, voila un example d'animation d'une page html à une autre sans aucune ligne de JS !](https://moritzglantz.de/multi-page-view-transitions-demo/index.html)

Cerise sur le gâteau, cette API est pleinement supportée, donc aucun problème à l'utiliser dès aujourd'hui !

<iframe class="ciu_embed" src="https://caniuse.pengzhanbo.cn/view-transitions#past=2&future=3&theme=light" height="492px" scrolling="no"></iframe>

[Voici un gros tutoriel plus complet en français pour apprendre à pleinement utiliser les View Transitions !](https://www.julienpradet.fr/tutoriels/view-transitions/)

(Pfiou ! beaucoup de liens pour celui-là, mais on en a forcément besoin pour comprendre la puissance du truc !)

### Temporal

Après 9 ans en cours de développement, l'API [Temporal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Temporal) est passée au Stage 4, ce qui signifie qu'elle est maintenant finale, et soit implémentée soit en phase finale d'implémentation dans tous les navigateurs !

[Je vous partage l'article de blog de Jason Williams, ingénieur chez Bloomberg et personne qui a eu le courage de bosser sur les dates pendant tout ce temps](https://bloomberg.github.io/js-blog/post/temporal/)

![=500x](/assets/posts/dev-digest-march-2026/temporal-cake.png)

<iframe class="ciu_embed" src="https://caniuse.pengzhanbo.cn/temporal#past=2&future=3&theme=light" height="458px" scrolling="no"></iframe>

&nbsp;

&nbsp;

Et voilà ! avec ça, je pense que vous avez de quoi jouer jusqu'au prochain article de veille, ou après m'être focus sur la partie HTML et CSS, je vais probablement me focus sur la partie JS !
