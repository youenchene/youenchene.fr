---
author: Youen Chéné
categories:
- retrogaming
- thomson
- reparation
date: "2026-04-21T04:27:00Z"
description: 
image: /post/images/thomson-mo5.jpg
name: Youen Chene
title: Thomson MO5 - Réparation démarrage
url: /2026/04/21/Thomson-MO5-reparation-demarrage

updated: "2026-04-20T04:27:00Z"
---

Aujourd'hui, le **Thomson MO5** : la version gomme de ce modèle, je ne l'ai vu qu'en panne dans ma petite école de campagne. 28 ans après, j'ai fait l'acquisition de ce modèle en touche "mécanique", mais il présentait des problèmes au démarrage.

![Photo d'un Thomson MO5](/post/images/thomson-mo5-photo.jpg)

## Diagnostic

Le symptôme était un boot instable : j'ai réussi à obtenir le BASIC une fois, mais après avoir tapé seulement quatre caractères, la machine a planté.


![Écran de boot avec des lignes jaunes et noires](/post/images/thomson-mo5-problem-boot-1.jpg)

![Écran de boot avec OK et des artefacts](/post/images/thomson-mo5-problem-boot-2.jpg)


{{< video src="/post/images/thomson-mo5-problem-boot-3.mp4" >}}

Suite au visionnage de [cette vidéo de redrum](https://youtu.be/7qxMdJrBttc?si=EqE7LGg5SO2C5-PV), j'ai commencé par vérifier l'alimentation. J'ai mesuré **24,7V au lieu des 17V** attendus. Cependant, le vendeur a testé ses autres alimentations qui font fonctionner ses propres MO5 et il obtient également 24,7V à vide. J'ai tout de même testé avec une autre alimentation (en 15V et 17V, en faisant attention à l'inversion de polarité spécifique au MO5), mais le résultat était identique.

## Résolution

### Tentatives infructueuses

Plusieurs pistes ont été explorées sans succès initial :
- Retrait et remise en place de la puce 8504.
- Nettoyage du bouton reset.

Le MO5 a refonctionné une fois démonté pendant 5 min, mais une fois remonté, le problème est revenu.

### Solution finale

La panne provenait finalement du **Gate Array EFGJ-033E**. Après avoir identifié ce composant comme suspect (voir les discussions sur [System-cfg ici](https://forum.system-cfg.com/viewtopic.php?t=16138) et [là](https://forum.system-cfg.com/viewtopic.php?t=9377)).

La manipulation est la suivante :
- Retrait avec douceur du Gate Array EFGJ-033E avec une pince adaptée.
- Nettoyage du socle et de la puce au nettoyant contact (du JelToSec, pas du WD40 ; le WD40 est bien trop gras pour une carte mère).
- Remise en place du Gate Array EFGJ-033E.


![thomson-mo5-cm.jpg](/post/images/thomson-mo5-cm.jpg)
_Note : ma carte mère est une version 3 de la carte mère du MO5._


Ça y est, il est stable. Plus qu'à attendre 10 min, le temps de charger un jeu avec le lecteur K7.
