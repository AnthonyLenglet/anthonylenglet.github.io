---
date: 2025-10-03
category:
  - Misc
tag:
  - Front
  - Vue
  - Framework
---

# A propos du blog

Yo !

Après la pause d'été (j'ai vraiment bien choisi mon moment pour commencer le blog moi), je reprend le blog en main, a partir de maintenant, il y aura un article de blog tout les vendredi de la dernière semaine du mois !

Je voulais d'ailleurs tous vous remercier pour l'incroyable reception du premier article, qui a reçus pas moins de **{{ Math.round(Math.random() * 1_000_000) + 100_000 }} impressions** et **{{ Math.round(Math.random() * 100_000) + 10_000 }} likes** tout réseaux confondus !

En commençant ce petit projet je n'aurais jamais cru atteindre autant de monde aussi rapidement, et ça me fait extrêmement plai-oula attendez j'ai un appel

> Allo ? oui ?... ah! ah ok!... non pas de soucis c'est pas grave ahah! ouais voila, ouais bisous! *click*...
> ...putain mais pourquoi je lui ai dis "bisous"...

RE ! bon c'était Roger, mon gars en charge des stats, apparemment ils se sont trompé, ils m'ont donnée des nombres "magique" qui change à chaque fois qu'on recharge la page (bref de la merde quoi)

Ah mais au fait, vous saviez que je pouvais faire des nombres aléatoires sur mes pages de blog ? Attendez je peux vous montrer Vuepress si vous voulez !

## Vuepress

### C'est quoi ?

Vuepress est un projet commencé par Evan You, créateur de Vue, en 2018, ayant pour but de faciliter la création de sites mi-statique/mi-spa, utile pour les docs et les blogs (c'est pour ça que je l'ai utilisé, t'as vu, pas con hein!)

l'avantage de ce mix statique/spa, c'est que ça nous donne la possibilité de commencer par quelque chose de simple, et si besoin d'ajouter quelques features un peu plus complexe à droite à gauche, sans pour autant rendre le blog inutilisable pour une personne moins tech-savy !

::: info
Les articles de blog ne sont que de simples fichiers markdown ! même une grand-mère peux écrire un article !
:::

![Une grand-mère dans son lit avec un ordinateur](/assets/posts/vuepress/grandma-computer.png 'moi (face reveal) dans mon bureau (lit) en train de rédiger cet article (futur best-seller New York Times)')

Bien sur, Vuepress n'est pas le seul dans sa catégorie, il y a eu d'autres framework du même style avant lui (notamment Gatsby), mais aussi après (Docusaurus, Angular Universal), même vue à une alternative, sous le nom de Vitepress !

Avec la sortie de Vue 3, Vuepress devait être déprécié pour devenir Vitepress, mais au final il à été décidé de donner Vuepress au main de la communauté, et l'équipe de Vue à fait de Vitepress un projet à part

### Les features

Vu que nous parlons d'un fichier markdown, nous avons bien sur la totalité des features de base de markdown, ce qui inclus :

**Tout** *les formattages* de ~~text~~ texte classique

- les listes a point

1. les listes numéroté

___
les séparateurs horizontal
___

> les citations
> > même imbriqué

| Feature | Opinion |
| ------ | ----------- |
| les tables | c'est cool |

Bien sur, je peux ajouter du code :

```md
**Tout** *les formattages* de ~~text~~ texte classique
```

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```

Jusque la, c'est standard, mais on peux ajouter des features via des plugins

:::info
Comme ces encarts !
:::

:::warning
:::

:::important
:::

:::tip
:::

:::caution
:::

::: tabs

@tab app.html

ou bien ces tabs

@tab coucou

<span style="font-size: 4em">beuh !</span>

:::

Je peux même faire des composants Vue custom et les ajouter dans un article, vous voulez faire vos achats ?

<Stepper></Stepper>

### "Mais dis donc Jammy, tu pense pas qu'on peux utiliser ça pour des projets clients ?"

Réalistiquement, oui, maintenant c'est vraiment adapté pour des clients qui cherche quelque chose qu'ils peuvent alimenter de façon autonome, avec la possibilité d'appeler des composants à leur guise dans leur articles.

::: info
Fun fact, Vuepress est l'inspiration principale dérrière un système mis en place chez un client avec qui j'ai travaillé, ou les personnes peuvent remplir un markdown, avec la possibilité d'ajouter des blocs réponses, ce qui ajoute un composant Angular !

![Un example de markdown avec un text entre balises "{{ }}" pour désigner les composants angular à ajouter](/assets/posts/vuepress/markdown-spa-code.png 'notez les balises `{{input}}` et `{{answer}}`')

![Le résultat visuel du markdown créé](/assets/posts/vuepress/markdown-spa-ui.png 'et voila les composants !')
:::

Tout ça pour dire, même si au final Vuepress / un framework `statique + spa` n'est pas adapté, il y a quand même des choses à retenir de l'idée, qui sait, il pourrait y avoir un besoin pour un format `spa + statique` quelque part dans vos projets !

## Bonus: les news et trouvailles de Septembre 2025

Avant de partir comme un voleur, je voulais faire un *petit* tour des nouveautés niveau veille que j'ai pu voir côté tech !

### Angular 20

Angular 20 est sorti en Août, amenant avec lui les signals en version stable ainsi que la dépréciation de `NgIf`, `NgFor` et `NgSwitch` !

Je ne vais pas m'attarder dessus vu que j'aimerais bien en faire le sujet d'un prochain article (probablement Novembre pour la sortie d'Angular 21)
mais je ne peux que vous conseiller d'explorer les signals, qui représentent l'un des plus gros ajouts du framework depuis le moteur Ivy d'Angular 8 selon moi !

### Boring Notch

Si vous avez vu un iphones récents, vous connaissez surement les animations satisfaisantes du notch

![Les animations du notch des Iphones](https://platform.theverge.com/wp-content/uploads/sites/2/chorus/uploads/chorus_asset/file/24002970/notch_animation.gif?quality=90&strip=all&crop=0,0,100,100)

Mais à savoir que les macs n'ont pas encore eu le droit à ce traitement, alors qui'ils ont eu aussi un notch
c'est la qu'intervient [Boring Notch](https://github.com/TheBoredTeam/boring.notch) !

![Un example des animations de Boring Notch](https://private-user-images.githubusercontent.com/33609792/477708210-2d5f69c1-6e7b-4bc2-a6f1-bb9e27cf88a8.gif?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTk1MDM3MzUsIm5iZiI6MTc1OTUwMzQzNSwicGF0aCI6Ii8zMzYwOTc5Mi80Nzc3MDgyMTAtMmQ1ZjY5YzEtNmU3Yi00YmMyLWE2ZjEtYmI5ZTI3Y2Y4OGE4LmdpZj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNTEwMDMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjUxMDAzVDE0NTcxNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTc3MjAxOGEyZWIwNWNhZjA5Yzk3NWVjM2E5OGZiNzRkZDUyNzg0YjI3MzBmM2E5Njc2YWJlMzNiYmE5YzA2MGMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.fMYvATotqyW8A0ScEohJqP4NNEFLQiQe3NngjDEkXBs)

Avec ce programme, vous gagnez accès au infos de l'audio en cours, un nouvel espace pour votre calendrier, des notifications pour la charge de votre mac, et même une zone "tiroir" pour stocker des fichier temporairement (sous-entendu tu va les mettre la et les oublier 3 mois plus tard, pour au final ne jamais les nettoyer, mais je critique pas hein... c'est juste un constat...)

![Le zone tiroir de Boring Notch](/assets/posts/vuepress/boring-notch.png)

### Bruno

Ok j'avoue que celui la je l'ai trouvé avant Septembre, mais j'ai vraiment commencé à l'utiliser que depuis Juillet, et c'est une excellente alternative open source à Postman !

![l'Interface de Bruno](https://www.usebruno.com/_next/image?url=%2Fbruno_app%2Fbruno-homepage.png&w=2048&q=75)

Toutes les features de base sont la, avec en prime une extension vscode, ainsi que la possibilité d'exporter les appels dans des fichiers `.bru`, permettant un versioning de ces dernières !
Il y a aussi un moyen d'ajouter des tests automatisé, par contre je n'ai pas encore eu le temps de tester cette partie *(en plus qui fait des tests quoi, bref...)*

[Le projet est disponible ici !](https://www.usebruno.com/)

___

Et avec ça, c'est la fin de cet article, si tu a aimé tout ça, n'oublie pas:

![Une animation d'abonnement youtube](https://cdn.pixabay.com/animation/2023/05/27/04/28/04-28-12-476_512.gif '**EXPLOSE CE BOUTON ABONNEMENT ET SONNE MOI CETTE CLO—**')
