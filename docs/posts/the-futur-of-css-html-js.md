---
date: 2025-11-21
category:
  - Veille
tag:
  - HTML
  - CSS
  - JS
---

# Les nouveautés des languages web (présent et futur)

Avec les avancées technologiques de ces dernières années, notre workflow a pas mal changé, notament avec l'arrivée des LLM;
il est maintenant plus simple que jamais de prendre une solution déjà faite à un problème et de vite passer a la suite.

Néanmoins, il est également plus simple que jamais d'ignorer les nouvelles améliorations des languages qu'on utilise quotidiennement,
et qui pourrait simplifier encore plus le code d'une IA entraînée sur de code stack overflow d'il y a 5 ans !

C'est pourquoi j'avais envie de commencer un petit tour d'horizon pour montrer les nouveautés déjà sorties ou sur le point de sortir côté HTML, CSS et JS — qui sait, peut-être que la solution à 20 lignes généré par Copilot pouvais être faite en 2 lignes grace à une feature sortie il y a 3 ans !

## HTML

### Elements formulaires personnalisable

l'un des plus gros point noir historique d'HTML est la suite de d'élément formulaire, qui nous force le look natif de l'OS sans possibilité de le personnaliser

C'est donc la qu'entre en scene le community group [Open UI](https://open-ui.org/), composé de développeurs et architectes travaillant sur Microsoft Edge, Google Chrome, Mozilla Firefox ainsi que plein d'autre personnes venant de petites boites lambda !

Leur objectif est très simple: proposer des nouveaux composants ou améliorations au composants actuel au WhatWG (le group groupe derrière la spécification HTML, parce que oui depuis 2019 le W3C ne gère plus la spec HTML, du coup une per— vous savez quoi ? je crois qu'il faudra que je vous présente un peu tout ça un jour !) afin de rendre ces derniers stylisable et extensible par tous !

### Select

Une de mes plus grosses obsessions dans le monde de la specification web depuis quelques années maintenant et l'élément select, élément utilisé dans toutes les apps que nous produisons, et qui malgrès ça requiert encore aujourd'hui un composant tiers pour pouvoir être customisé

c'est la que la specification [`<selectlist>`](https://open-ui.org/components/customizableselect/) entre en jeu !

Au départ pensé comme un élément `<selectmenu>`, puis `<selectlist>`, pour finalement être une réelle extension du composant `<select>`, cette specification nous permet enfin de se débarrasser de toute ces librairies npm externe ayant tous une api similaire mais pas trop, non maintenu depuis 8 ans avec 57 packages en dépendances !

<iframe height="600" style="width: 100%;" scrolling="no" title="Custom &lt;select&gt; examples" src="https://codepen.io/argyleink/embed/wvYrZEV?default-tab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true"></iframe>

### Rangegroup

hey, vous avez déjà utilisé cet élément ?

<input type="range" min="0" max="100" step="10" list="values"/>
<datalist id="values">
  <option value="10" label="low"></option>
  <option value="90" label="high"></option>
</datalist>

il est probable que non, il est aussi probable que ça ne soit pas du à un manque de besoin, mais à un manque de features, voila donc la deuxième spec, [Enhance Range Input](https://open-ui.org/components/enhanced-range-input.explainer/) !

[voici une demo de la totalité des nouvelles features](https://brechtdr.github.io/enhanced-range-slider-poc/)

![plusieurs ancres de selections, enfin !](/assets/posts/the-futur-of-css-html-js/multirange.png)

::: info
A savoir que `<input type="range">` [dans la spec originale W3C HTML 5.1](https://www.w3.org/TR/2016/WD-html51-20160310/single-page.html#range-state-typerange):

- devait supporter l'attribut `multiple`
- devait supporter l'orientation verticale si hauteur > largeur
- devait supporter la labellisation des étapes (les tirets sous l'input range montré plus haut)

mais les navigateurs non juste jamais implémenté les features, me demandais pas pourquoi !
:::

### Combobox

Au cas ou vous ne l'avez vu, je vous présente l'element le plus inutile encore dans la spec HTML actuellement

<select name="pets" multiple size="4">
  <optgroup label="Animaux à 4-jambes">
    <option value="Chien">Chien</option>
    <option value="chat">Chat</option>
    <option value="hamster" disabled>Hamster</option>
  </optgroup>
  <optgroup label="Animaux volants">
    <option value="perroquet">Perroquet</option>
    <option value="macaw">Macaw</option>
    <option value="albatros">Albatros</option>
  </optgroup>
</select>

Ceci est un element select avec l'attribut `multiple`, respirez, ça va aller, il peux pas vous faire de mal, il a juste un petit truc en plus, c'est tout

Blague a part, oui, l'utilisation prévu de ce composant est de sélectionner plusieurs options dans la liste en faisant un `ctrl + click` ou `alt + click` sur les options, je suis sur que les utilisateurs vont comprendre ça !

Pour remédier à ca (mais pas que !), la nouvelle spec `spec` a pour projet d'ajouter le support pour l'attribut `multiple`, mais voici également la spec [Combobox](https://open-ui.org/components/combobox.explainer/), qui permetterait d'ajouter une fonction de recherche a vos elements `<select>` en les liant avec un `<input>` !

l'example utilisé par la spec est la liste de labels de Github:

![Bientôt dans un navigateur près de chez vous ! =300x](/assets/posts/the-futur-of-css-html-js/githublabels.gif)

le code proposé ressemblerait à ça

```html
<input filter=select>
<select id=select size=4>
  <option>one</option>
  <option>two</option>
</select>
```

ceci n'est pas la seule évolution proposé par la spec, car l'autre focus est aussi sur la stylisation des choix proposé par un input lorsqu'il est agrémenté par un élément `<datalist>`

<input list=datalist placeholder="select an option">
<datalist id=datalist>
  <option>one</option>
  <option>two</option>
</datalist>

A l'heure actuel, nous ne pouvons rien customisé , mais l'idée serait de pouvoir en faire quelque chose de ce style !

![=500x](/assets/posts/the-futur-of-css-html-js/githubsearch.gif)

### Switch

Vous voyez les switch ?

![Ces fameux boutons la](/assets/posts/the-futur-of-css-html-js/switch.png)

[Voici une spec pour les ajouter de façon officielle en tant que composant `<switch>`](https://open-ui.org/components/switch.explainer/)

Une implémentation via `<input type="checkbox" switch>` avais également été proposé côté WHATWG (et [existe sur Safari Technology Preview et Safari Beta](https://github.com/whatwg/html/pull/9546#issuecomment-1865357407)), mais pour le moment, cette spec est encore en discussion actif, affaire a suivre donc !

## CSS

### `:has()`

Cette pseudo-class permet de styliser un élément parent basé sur un élément enfant, c'est le fameux sélecteur parent que beaucoup dans la communauté demandais depuis is longtemps !

[Post Stack Overflow il y a 16 ans: "Is there a CSS parent selector?"](https://stackoverflow.com/questions/1014861/is-there-a-css-parent-selector)
[Mail au commité W3C de 1999: "Re: Why no Parent Selector?"](https://lists.w3.org/Archives/Public/www-style/1999Dec/0007.html)

En guise d'exemple, cette pseudo-class est utilisé sur le projet Oney HIVE, ou je change la couleur de l'arrière-plan d'une chaîne de commentaires de revue d'un projet, si une des réponses est une validation ou un refus du projet !

```scss
.thread {
  padding-left: 18px;

  &:has(> article > .comment > .Compliant),
  &:has(> article > .comment > .Validate) {
    border-left: 2px solid $oney-dark-lime-green;
  }

  &:has(> article > .comment > .Non-compliant),
  &:has(> article > .comment > .Refuse) {
    border-left: 2px solid $oney-cherry;
  }

  &:has(> article > .comment > .Not_Applicable) {
    border-left: 2px solid $oney-browny-orange;
  }
}
```

il est aussi utilisé pour changer la couleur d'un label si un input est actif ou sélectionné

```scss
label {
  &:has(input:checked) {
    border-color: $green-400;
    box-shadow: 0px 2px 2px 0px rgba(0, 0, 0, 0.25);
    translate: 0 -4px;
  }

  &:has(input:focus) {
    outline: 2px solid $green-400;
    outline-offset: 2px;
  }
}
```

Bref, si il y a élément à retenir aujourd'hui selon moi, c'est lui !

### Container Queries

Les containers queries ont déjà fait l'objets d'énormément de posts dédié a lui seul, et je pense qu'aucune introductions que je pourrais écrire viendrait a la cheville de l'excellent [article de Josh Comeau](https://www.joshwcomeau.com/css/container-queries-introduction/), je ne peux que vous conseiller de l'explorer !

Mais pour la faire courte, le but de cette feature est de donner des styles différents à vos composants selon la taille de leur conteneur !

En guise d'example, aujourd'hui, Youtube utilise deux composants différent pour ces vidéos sur la page d'accueil et dans leur sidebar

![Sur la page d'accueil on a ça](/assets/posts/the-futur-of-css-html-js/container-queries-1.png)

![Et quand on est sur une vidéo on a ça sur le côté](/assets/posts/the-futur-of-css-html-js/container-queries-2.png)

Avec les container queries, on pourrait en faire un seul et même composant qui change de style selon la longueur du conteneur dans lequel il est placé !

## JS

### Iterator Chunking

Alors déjà, si vous ne connaisais pas les Itérateurs, petite aparté rapide:

Il est probable que vous ne voyiez jamais un code utilisant réellement les itérateurs, même si elles ont leur utilité !

Par example, voici un code permettant de boucler sur une liste d'utilisateurs dans un Azure Active Directory, ou l'appel http est paginé

```ts
function async *paginatedMemberList(
  groupId: string,
): AsyncGenerator<ODataResponse<AzureUser>, void, void> {
  let result = undefined;
  let nextPageUrl = `https://graph.microsoft.com/v1.0/groups/${groupId}/members`;
  do {
    result = await lastValueFrom(
      this.httpService.get(nextPageUrl, {
        headers: { Authorization: `bearer ${this.token}` },
      }),
    );
    yield result.data;
    nextPageUrl = result.data['@odata.nextLink'];
  } while (nextPageUrl);
}
```

les fonctions itératrices commencents par une étoile, et utilisent le mot clé `yield` au lieu de `return`, c'est la même chose, on retourne une valeur, mais `yield` permet une chose en plus: de continuer la fonction plus tard !

voici comment la fonction est appelé:

```ts
for await (const page of this.paginatedMemberList(this.groupAzureID)) {
  for (const ADuser of page.value) {
    this.checkADuser(ADuser);
  }
}
```

Quand vous faite un `for...of`, la valeur après un of doit être un objet itérable, comme une liste dans la majorité des cas.

A chaque début de boucle, le moteur js appel l'itérateur, récupère la valeur retourné par `yield`, et effectue son fonctionnement avec cette valeur
a la fin de cette boucle, elle appelle la methode `.next()`, qui continue la fonction la ou elle c'est arrêté avec `yield` !

Les itérateurs créée manuellement sont très spécifique, mais permettent de rendre le code tellement propre si utilisé à bon escient !

&nbsp;

&nbsp;

Bref, avec cette courte introduction, voici la feature proposé:

```js
let str = ""
for (let num of [1,2,3,4,5]) {
  str += num
}
```

Ici, la liste va être itéré, mais pour le moment, il nous est impossible de sortir les nombres 2 par 2, ou 3 par 3, ou 4 par 4, ou 5 par 5, ou 6 pa-

[Voici la proposition pour "l'iterator chunking" !](https://github.com/tc39/proposal-iterator-chunking)

```js
const digits = () => [0, 1, 2, 3, 4, 5, 6, 7, 8, 9].values();

let chunksOf2 = Array.from(digits().chunks(2));
// [ [0, 1], [2, 3], [4, 5], [6, 7], [8, 9] ]

let chunksOf3 = Array.from(digits().chunks(3));
// [ [0, 1, 2], [3, 4, 5], [6, 7, 8], [9] ]

let chunksOf4 = Array.from(digits().chunks(4));
// [ [0, 1, 2, 3], [4, 5, 6, 7], [8, 9] ]
```

avec cela, vous pourrez donc boucler sur votre liste avec vos infos groupés tel que vous le souhaitez !

d'ailleurs, si vous voulez une telle feature, vous pouvez le faire aujourd'hui avec ce code

```ts
function *chunkArray(arr: unknown[], size: number) {
    let arrCopy = [...arr];
    while(arrCopy.length >= 1) {
        yield arrCopy.splice(0, size);
    }
}

for(let items of chunkArray([0,1,2,3,4,5,6], 2)) {
    console.log(items);
}
```

::: info
la specification permet aussi de grouper avec les valeurs précédentes !

```js
let windowsOf2 = Array.from(digits().windows(2));
// [ [0, 1], [1, 2], [2, 3], [3, 4], [4, 5], [5, 6], [6, 7], [7, 8], [8, 9] ]

let windowsOf3 = Array.from(digits().windows(3));
// [ [0, 1, 2], [1, 2, 3], [2, 3, 4], [3, 4, 5], [4, 5, 6], [5, 6, 7], [6, 7, 8], [7, 8, 9] ]

let windowsOf4 = Array.from(digits().windows(4));
// [ [0, 1, 2, 3], [1, 2, 3, 4], [2, 3, 4, 5], [3, 4, 5, 6], [4, 5, 6, 7], [5, 6, 7, 8], [6, 7, 8, 9] ]
```

:::

### Typage JS

**OUI !** [Je vous jure que c'est en cours pour de vrai !](https://github.com/tc39/proposal-type-annotations)

l'équipe derrière Typescript est en discusion avec le commité Ecmascript pour ajouter les typages de manière natif en JS !

Alors attention, les typages serait interprété comme des commentaires pas les moteurs JS, ce qui veux dire que les navigateurs les ignorerait, l'utilisé serait surtout pour les éditeurs de code de ne plus avoir à intégrer tout un interpréteur typescript lent, le bénéfice principale pour nous serait donc un gain de performance important ainsi qu'une adoption officielle des typages dans l'écosystème Javascript !

## Et plus encore !

Je pourrais faire durer de post tellement plus longtemps, j'ai du couper ce post qui me faisait partir dans beaucoup trop de recoins obscurs que sont les specs techniques, attendez vous donc a voir plus d'une suite à ce post, mais en attendant, je ne peux que vous conseillez d'explorer par vous même toutes les nouveautés en cours de développement, nous n'avons jamais vu autant d'évolutions en même tem- **ILS AJOUTENT DES IF AU CSS, PARDON ??**

Non il faut vraiment que je m'arrête la pour aujourd'hui, à plus tard pour le prochain article, on parlera d'Angular 21 !
