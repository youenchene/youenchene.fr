---
author: Youen Chéné
categories:
- retrogaming
- thomson
- reparation
date: "2026-04-10T00:00:00Z"
description: 
image: /post/images/thomson-to7-70-photo.jpg
name: Youen Chene
title: Thomson TO7/70 - Réparation Clavier
url: /2026/04/10/Thomson-TO7-70-reparation-clavier

updated: "2026-04-10T00:00:00Z"
---

Aujourd'hui, une réparation du clavier d'un Thomson TO7/70. Ce modèle mythique de l'informatique française des années 80 que j'ai connu en CE2 pendant le plan Informatique pour Tous.

![Photo d'un Thomson TO7/70](/post/images/thomson-to7-70-photo.jpg)

## Diagnostic

Certaines touches du clavier ne répondent plus du tout. La ligne STOP, 1, 2, 3, 4, 5, mais aussi des touches de manière aléatoire sur le clavier.

En repartant de l[a vidéo de réparation de Rodrik](https://youtu.be/6hgD07mC5yg?si=Zgw2eSBRNoSNFA6k), je consulte la documentation de la nappe du clavier et j'identifie rapidement que j'ai 2 pistes qui sont coupées : la piste 7 sur le port A et la piste 7 sur le port B. 

![Vue de la nappe du clavier Thomson](/post/images/nappe-clavier-to7-70.jpg)

Après un contrôle au multimètre, les pistes sont effectivement coupées. Et mauvaise nouvelle, les pistes sont très fragiles. Passons à la résolution.

## Résolution

### Tentative 1 : le crayon de reconstruction de pistes

Je tente une réparation au crayon de reconstruction de pistes acheté pas cher.

Cette tentative est un désastre, cela ne tient pas, cela part au premier frottement, pire les tests de conduction ont abîmé d'autres pistes.

![Photo de la nappe au microscope numérique de la tentative de raccordement via le crayon](/post/images/nappe-to7-70-pen.jpg)

### Tentative 2 : le ruban adhésif conducteur

Après cette défaite, la situation initiale s'est dégradée : encore moins de touches fonctionnent. Je pars sur une autre solution (aussi issue de la vidéo de Rodrik) : l'utilisation de ruban adhésif conducteur en cuivre. (Référence : [Bandes de feuille de cuivre 8PCS, adhésif conducteur double face pour le blindage EMI, anti-limaces, circuits de papier](https://amzn.to/4spaclT)).

Je passe donc au collage sur les pistes défectueuses. En voici le résultat :

![Photo de la réparation de la nappe au ruban de cuivre](/post/images/reparation-nappe-to7-70.jpg)

Cela fonctionne, c'est parti pour tester la cartouche MEMO7 **MEGAROM T2** ! (Et cela fera l'objet d'un autre article)
