---
date: 2026-01-21
category:
  - Veille
tag:
  - Angular
---

# Angular 21(.1 !)

Sonnez les cloches, ouvrez les fenêtres, dégivrez de nouveau Mariah Carey parce que

![Mariah Carey screaming "It's Time !"](/assets/posts/angular-21/its-time.gif 'Alternativement: il est l\'or monseignor !')

On a une nouvelle version d'Angular, et il y a des choses assez cool à voir, dont une annonce particulièrement intéressante que je nous garde pour la fin !

Bon en vrai cet article ne sera pas que sur des nouveautés de la version 21, vu qu'on est en train de construire sur des bases auxquels vous n'êtes pas forcément familier si vous n'avez pas touché au nouvelles features des 3/4 dernières versions, mais promis je reste concis cette fois !

Depuis le temps, je pense que vous en avait entendu parler, mais au cas ou, faisont un petit détour par une courte présentation des signals, histoire d'être sur d'être tous à la même page

## Les signals

Pour faire cours Les signals sont un conteneur pour une valeur qui notifie les composants l'utilisant quand la valeur est mise à jour.

Alors la vous vous dites probablement "mais attend, c'est pas des observables du coup ?", ce à quoi je vous réponds que plus ou moins oui !

```ts
export class ExampleComponent {
  firstValue = signal(0);
  secondValue = signal(0);
  result = computed(() => Number(firstValue) + Number(secondValue));

  incrementFirstValue() {
    firstValue.update((value) => Number(value) + 1);
  }
}
```

```html
<label for="first">Enter the first value:</label>
<input id="first" [(ngModel)]="firstValue"/>
<button (click)="incrementFirstValue()">Increment first value</button>

<label for="second">Enter the second value:</label>
<input id="second" [(ngModel)]="secondValue"/>

<span>result: {{count}}</span>
```

Pour la large majorité des cas, ce qui est historiquement fait avec des observable dans Angular peux être traduit assez simplement en signals, et le code qui en ressort est beaucoup plus lisible, notament dû au fait que la totalité des modifications normalement effectué dans la fonction `pipe()` sont remplacé par une seule fonction `computed()`, qui écoute automatiquement tous les signals utilisé dans la fonction pour des changements et relance la fonction dès qu'elle en détecte une !

```ts
const observableExample = of([4,6,2,5,1,3])
  .pipe(
    map((value) => {
      return value.sort();
    })
  ).subscribe();

const signalsExample = signal([4,6,2,5,1,3]);
const computedExample = computed(() => {
  return signalsExample.sort();
});
```

Les valeurs des observables sont toujours envoyé dans une liste, d'ou le fait qu'on ai besoin de passer par un map pour acceder à notre valeur, ce qui n'est plus le cas avec les signals !

:::info
il existe aussi `effect()`, qui est comme `computed()`, à la difference qu'il ne resort pas de valeur, à utiliser lorsque vous voulez juste lancer une fonction en réponse à un changement de valeur !
:::

Globalement, il faut juste ce dire que le plan long terme d'Angular et de ne garder les observables que pour les cas super complexe qui demande vraiment l'utilisation d'un observable (ouvrir un canal d'informations qui arriverons dans le temps, et pouvoir planifier le filtrage en amont ainsi que la façon dont l'information est partagé au reste de l'application)
Côté Angular natif, cela signifie qu'à long terme, les observable seront limité aux retour de requête HTTP et les formulaires complexe, et justement, en parlant des formulaires...

## Les formulaires signals

Pour les formulaire de tout les jours, voici maintenant une façon plus simple (et censé) de faire un formulaire avec typage et validations !

```ts
import { Component, signal } from '@angular/core';
import { FormField, form, email, required } from '@angular/forms/signals';

interface LoginData {
  email: string;
  password: string;
}

@Component({
  imports: [FormField],
  template: `
    Email: <input [formField]="loginForm.email">
    Password: <input [formField]="loginForm.password">
  `
})
export class LoginForm {
  login = signal<LoginData>({
    email: '',
    password: ''
  });
  
  loginForm = form(this.login, (schemaPath) => {
    required(schemaPath.email);
    email(schemaPath.email);
  });
}
```

La nouvelle fonction `form()` prend un signal, représentant son format, ainsi une fonction supplémentaire optionelle (qui reçois un `schemaPath` contenant le chemin vers les valeurs du formulaire) permettant de configurer la validation des champs individuel !

Dorénavant, la création de mécanisme de validation customisé sera beaucoup plus simple, et le typage deviens juste une interface classique sans besoin de penser à `FormControl` ou `FormGroup` !

## Bye bye zone.js

Poussé vers la sortie depuis Angular 18, Angular 21 sonne le glas pour Zone.js

Pour les personnes qui ne savent pas vraiment ce que faisait Zone.js dans vos applications, c'était une librairie ayant pour but de detecter tout les changements côté code js qui pourrais affecter de prêt ou de loin le rendus de l'interface et de lancer un redessinage de la page dans ce cas, afin de s'assurer que l'interface et le code reste synchro

Typiquement, sans Zone.js, ce compteur ne se metterais pas à jour visuellement:

```ts
@Component({
  selector: 'app-root',
  template: `
    <button (click)="updateCounter()">Click me</button>
    <p>{{counter}}</p>
  `,
})
export class AppComponent {
  counter = 0;

  updateCounter() {
    this.counter++;
  }
}
```

Mais bien sur, cela ne venais pas sans aucun drawback, notament le fait que les Zone.js à tendance à surfaire le travail ainsi qu'a apporter son lot de problème de performance (suivre non-stop les valeurs de toutes les variables de l'application + les requêtes html + les évènements utilisateurs + les timers js peux avoir tendance à faire ça effectivement)

Initialement, il avais été considéré comme un bon tradeoff à avoir, mais au fil du temps (et notament avec les signals), il à été décidé que se débarrasser de Zone.js était le bon choix

dorénavant, il vous faudra faire usage des signals pour cet example !

```ts
@Component({
  selector: 'app-root',
  template: `
    <button (click)="updateCounter()">Click me</button>
    <p>{{counter}}</p>
  `,
})
export class AppComponent {
  counter = signal(0);

  updateCounter() {
    this.counter.update(value => value++);
  }
}
```

## Vitest par défaut

Les outils de tests côté Angular ont toujours été un point faible, et nombreux sont les personnes qui remplaçais Karma et Jasmine par une alternative tel de Jest et Cypress

Avec Angular 21, tout ça change enfin, parce que Vitest deviens le framework de choix par défaut des nouvelles applications Angular, et un outil de migration est rendu disponible pour les anciennes apps

```sh
ng g @schematics/angular:refactor-jasmine-vitest
```

Merci pour les travaux, Jasmine et Karma, maintenant on peux partir de l'avant avec des outils moderne !

## Angular Aria

Le meilleur pour la fin !

[Angular Aria](https://angular.dev/guide/aria/overview) est une nouvelle librairie de composant headless faite par l'équipe d'angular pour les applications ayant besoin de leur propre design systems

Vu que je suis un Oracle apparemment, je ne peux que vous conseiller [mon premier article sur ce blog](/posts/headless-ui-library.html), qui présente en profondeur ce sujet (et aussi pour des examples concret de composant)

Retenez juste que à partir de maintenant, le meilleurs moyen de développer des composants est en partant de ces composants non stylisé, car ils gèrent la totalité des demandes d’accessibilité pour vous, et seront toujours mis à jour vis à vis de la dernière version d'Angular, le tout sans contrepartie !

Les composants actuellement disponibles sont:

- Les Accordéons

![Un example d’élément accordéon =300x](/assets/posts/angular-21/accordion.png)

- Les Combobox (combo input + popup)

![Un example d’élément combobox =300x](/assets/posts/angular-21/combobox.png)

- Les Grilles (utile en tant que base pour des grilles avec cases à taille variable, version plus complexe des élément `<table>`, ou alors un calendrier)

![Un example d’élément grille (avec la navigation clavier déjà géré !) =300x](/assets/posts/angular-21/grid.gif)

- Les listbox

![Un example d’élément listbox =300x](/assets/posts/angular-21/listbox.png)

- Les menus déroulants

![Un example d’élément menu =300x](/assets/posts/angular-21/menu.png)

- Les tabs

![Un example d’élément tabs =300x](/assets/posts/angular-21/tabs.png)

- Les toolbars

![Un example d’élément toolbar =300x](/assets/posts/angular-21/toolbar.png)

- Les Arborescences

![Un example d’élément arborescences =300x](/assets/posts/angular-21/tree.png)

Plus besoin d'une librairie externe pour ces composants, et ça va continuer à arriver !

![🎉🎉🎉](/assets/posts/angular-21/yipee.gif)

## A venir: les améliorations du compilateur de template

Avec Angular 21.1 et .2 sur la route, les changements qui commencent à sortir laisse suggérer un focus sur le compilateur de template, avec l'ajout du supports pour plusieurs syntaxes javascript (opérateurs spread, instanceof, fonctions fléchées); est-ce que c'est juste un petit sujet de pasage, ou est-ce signe d'un plus gros focus sur le mix du code js et du code template dans le même fichier ?
Cela reste à voir, mais de mon côté, je restes au aguets !

Bon, c'est pas tout ça, mais j'ai des mises à jour à faire, et un 5ème element select à faire, du coup je vais vous laisser avec les premiers croquis de la potentielle nouvelle mascotte d'angular ! soyez gentil avec lui, et ne lui faites pas peur, je compte sur vous !

![Croquis de la nouvelle mascotte Angular](/assets/posts/angular-21/angular-mascot.png)
