---
theme: apple-basic
highlighter: shiki
title: Introduction au développement d’applications web interactives avec XState

layout: intro
---

# C'est quoi... XState ?

Une nouvelle version de X-Files ou X-Men ? 🤔

<div class="absolute bottom-10">
  <span class="font-700">
    Baptiste Devessier - 2023
  </span>
</div>

---

# Demo

<a href="https://xstate-talk-todo-app.netlify.app" target="_blank">

![](/Screenshot%202023-01-23%20at%2011-05-42%20https%20__xstate-talk-todo-app.netlify.app.png)

</a>

---

# Structure de l'application

- Récupération des todos dès que la page est affichée
- Code *défensif* pour empêcher certains comportements, comme l'ouverture du formulaire uniquement si un booléen a une certaine valeur
- Des booléens doivent être synchronisés à partir de différents endroits
- Parfois, une fonctionnalité est si complexe à implémenter que le code devient dur à déchiffrer, comme l'appel de `synchronizeTodoList`

<!--
Open VSCode with code for /without-xstate page

- Date fetching
- Prevent from opening the form during initial loading
- Need to 
-->

---
layout: intro
---

# Un autre monde est possible.

Un monde fait de state machines.

---

# C'est quoi les state machines?

- Un nombre fini d'*états*
- Un seul état à la fois
- Un état *initial*
- En attente d'événements
- Les événements déclenche des *transitions* d'un état à un autre
- Les transitions sont *déterministes* : la même séquence d'événements produire toujours le même résultat

---

# Une state machine

<a href="https://stately.ai/registry/editor/6fa98cfb-fe39-4479-a6a6-2db09dc872d1?machineId=d530e75e-35d7-4e78-a67f-56f6b64b6eab" target="_blank">

![](/CleanShot%202023-01-22%20at%2016.33.05%402x.png)

</a>

---

# Au final... c'est quoi XState?

- https://stately.ai/docs (🆕 Nouvelle documentation mise en ligne la semaine dernière !)
- Une librairie pour créer des state machines en JavaScript/TypeScript
- Peut être utilisé partout où du JavaScript peut tourner (navigateur, Node.js, NodeBots, Temporal Workflows, etc...)
- Dans le navigateur, peut être utilisé avec n'importe quel framework, et même en Vanilla !
- [Stately](https://stately.ai) développe des outils visuels pour XState

---
layout: section
---

# Réimplémentation avec XState

---

# Avantages de la réimplémentation

- La logique est centralisée dans une machine
- Les *event handlers* ne font que retransmettre des événements à la machine, et ne contiennent plus de logique
- La vue dérive des données de l'état actuel de la machine
- Le contexte est utilisé pour stocker des données non-finies, comme la liste des todos

---
layout: section
---

# Un autre exemple ?

---

# Avantages et inconvénients de XState

<br>

<div class="grid grid-cols-2">
<div>

## Avantages

- La logique de l'application est centralisée et isolée des détails d'implémentation
- La logique est plus facile à comprendre, et d'autant plus avec les outils visuels
- La logique est prédictible : seulement ce qui est défini dans la machine peut se produire
- D'autres personnes que des développeurs peuvent comprendre le code, et même y contribuer !

</div>

<div>

## Inconvénients

- Cela peut prendre du temps pour être efficace avec XState
- Le paradigme n'est pas encore très répandu dans le milieu du développement front, cela peut nécessiter certains efforts pour que toute une équipe l'adopte

</div>
</div>

---

# XState peut faire encore plus

- Des librairies pour tous les frameworks front-end : @xstate/react, @xstate/vue, @xstate/svelte, @xstate/solid (bientôt)
- [@xstate/inspect](https://stately.ai/docs/tools/inspector) : Inspecter une machine en temps réel et interagit avec elle
- [@xstate/test](https://stately.ai/docs/xstate/packages/xstate-test) : Générer des tests à partir d'une state machine (Model-Based Testing)
- [Orchestrer une CLI faite avec Node.js](https://github.com/mattpocock/matt-cli/blob/13953df17e05213bff1f69fb1e9e416a3996171a/src/pr.ts)
- [Dans un serveur Node.js](https://youtu.be/qqyQGEjWSAw)
- [Dans un Workflow Temporal](https://github.com/Devessier/temporal-electronic-signature)
- Et prochainement... avec d'autres langages que le JavaScript

---

# Pour en savoir plus

- https://stately.ai
- https://statecharts.dev

---

# Merci !

Merci 42 d'avoir accepté ma présentation !

- <mdi-github /> [Devessier](https://github.com/Devessier)
- <mdi-link /> [baptiste.devessier.fr](https://baptiste.devessier.fr)
- <mdi-twitter /> [BDevessier](https://twitter.com/BDevessier)
- Code : https://github.com/Devessier/xstate-talk-demo
