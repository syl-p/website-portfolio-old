---
layout: Post
title:  Nodejs, la solution parfaite pour une startup ?
published:   2018-08-07
tag: Startups dev nodejs
author: Sylvain Pastor
comments: true
img: nodejs.png
description: AHH Nodejs… La REVOLUTION d’après ce qu’on voit sur le web. Linked, Airbnb, Uber et même la NASA en ont fait leur arme de prédilection...
---
![Nodejs](../.vuepress/public/img/uploads/nodejs.png)

AHH Nodejs… La REVOLUTION d’après ce qu’on voit sur le web. Linked, Airbnb, Uber et même la NASA en ont fait leur arme de prédilection. Par corrélation, Beaucoup de petites entreprises et de startups suivant leurs exemples, choisissent de tirer parti de cette technologie pour créer leurs applications. Mais est ce que c’est une bonne idée ? C’est ce que nous allons essayer de déterminer aujourd’hui.


## Node, est ce que c’est une révolution ?


Oui et encore oui ! En effet on parle d’opération I/O (entrée/sortie) non bloquantes, ce qui signifie en soit que grâce à la programmation asynchrone permise par le moteur Javascript V8, une opération n'empêchera pas l’exécution d’une autre.

``` js
var mongoose = require('mongoose');
var Page = require('../models/page.js');

exports.get = function(req, res) {

  // 1 -> renvoie des données (plus long que l’action 2)
  return Page.find(function(err, pages) {
  	 [...]
  });

  // 2 -> action rapide à faire,  s'exécutera plus rapidement que la première action.
  print(‘hello world’);

};
```

Dans cet exemple, si la recherche des données prend trop de temps ou renvoie une erreur, le **print(‘hello world’)** s'exécutera quand même sans attendre que la première opération soit terminée.

Pour reprendre l’exemple d’[open class room](https://openclassrooms.com/courses/des-applications-ultra-rapides-avec-node-js/node-js-mais-a-quoi-ca-sert):
Ceci est du code bloquant, situation que l’on rencontre souvent avec des technologies comme PHP, Ruby...

```
Télécharger un fichier
Afficher le fichier
Faire autre chose
```


Et ça est du code non bloquant

```
Télécharger un fichier
    Dès que c'est terminé, afficher le fichier
Faire autre chose
```

## Vitesse, amélioration de l'expérience développeur
La programmation asynchrone et le traitement non bloquant offrent une meilleure expérience utilisateur. Les tâches peuvent s’exécuter en arrière-plan, tandis que l'utilisateur interagit avec d'autres fonctionnalités. Cela rend Node.js idéal pour les applications nécessitant une réponse rapide.

Mais pourquoi choisir Node.js pour une startup ? Principalement pour l’efficacité de son écosystème. L'utilisation du même langage, JavaScript, côté serveur et client, permet une cohérence et un confort intellectuel pour les développeurs. Une équipe plus efficace signifie une réduction des coûts de développement, ce qui explique pourquoi tant de startups adoptent Node.js.

Cependant, il est essentiel de comprendre dans quels cas Node.js excelle et où ses performances peuvent être limitées.
![Voir le top des technologies utilisées par les devs](../.vuepress/public/img/uploads/technologies.jpg)

Source : [Thenewstack](http://thenewstack.io/javascript-popularity-surpasses-java-php-stack-overflow-developer-survey/)


## Node.js, la technologie parfaite pour les startups
Node.js est particulièrement bien adapté aux startups pour plusieurs raisons :
- **Rapidité de développement** : Avec un environnement basé sur JavaScript des deux côtés (client et serveur), Node.js permet de réduire la courbe d'apprentissage et d'accélérer le développement. Les startups, souvent en manque de temps et de ressources, peuvent ainsi lancer rapidement des MVP (produits minimum viables) sans avoir à recruter plusieurs équipes de développeurs pour différents langages.
- **Coûts réduits** : En utilisant une seule et même technologie, Node.js permet de diminuer les coûts de développement et de maintenance. L'écosystème JavaScript est riche en bibliothèques et en outils open source, ce qui permet aux startups d'accéder à des solutions performantes sans avoir à investir dans des outils coûteux.
- **Scalabilité** : Node.js est conçu pour gérer des applications à grande échelle. Grâce à sa nature asynchrone, il est capable de traiter un grand nombre de connexions simultanées avec une faible consommation de ressources. Cela permet aux startups de lancer leurs produits et de les faire évoluer sans devoir refondre l’architecture au fur et à mesure que leur base d’utilisateurs grandit.

Communauté et support : Node.js bénéficie d'une large communauté de développeurs, offrant un support continu et un écosystème riche de modules prêts à l'emploi via NPM (Node Package Manager). Cela permet aux startups de s'appuyer sur des solutions éprouvées tout en se concentrant sur l'innovation.

En résumé, Node.js est parfait pour les startups car il permet de développer rapidement des produits, de les faire évoluer sans grande complexité, et tout cela à moindres coûts.

## Mode "temps réel" activé !
Node.js brille particulièrement lorsqu'il s'agit de traiter un grand volume de données légères (messages, likes, connexions utilisateurs, etc.) et d'afficher ces informations en temps réel. Ce modèle est à la base des applications en temps réel (RTA).

Voici quelques exemples d'applications RTA :
* Trello
* Dropbox paper
* Google drive
* Messenger
* ...

UUn module très populaire pour gérer le temps réel avec Node.js est Socket.io. Il permet une communication **bidirectionnelle** en temps réel entre le serveur et le client, indispensable pour les RTA.

## Les limites : gestion intensive du CPU
Les opérations nécessitant une puissance de calcul intensive bloqueront les requêtes entrantes, rendant le principal avantage de Node.js caduc. Si vous devez développer un logiciel nécessitant une gestion intensive du CPU, optez pour une autre technologie plus adaptée.

## NodeJs, une modularité sans limite
Grâce au [manager de packet NPM](https://www.npmjs.com/), vous avez accès à une vaste collection de modules open source. Ces modules vous permettent d’ajouter facilement de nouvelles fonctionnalités à vos applications. Parmi les nombreuses pépites, vous pouvez parfois tomber sur des outils surprenants.

Par exemple, j’ai récemment découvert le module [Player](https://www.npmjs.com/package/player), qui permet de lire des fichiers audio sur la machine hébergeant le serveur Node.js. C’est parfait pour développer des dispositifs interactifs ou musicaux !

## #JeSuisDevNodeJS
En conclusion, lorsque l’utilisation de Node.js est justifiée, cette technologie peut représenter un atout majeur pour les startups, en particulier en matière d’efficacité et de rapidité d’évolution.

JavaScript est déjà un langage incontournable pour les interfaces web dynamiques (grâce à des frameworks comme AngularJS, React, Vue.js). Son utilisation côté serveur via Node.js permet aux entreprises de se démarquer avec des applications performantes et aux jeunes développeurs de développer des compétences à la fois polyvalentes et pointues dans l’univers du digital.