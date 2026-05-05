---
author: Youen Chéné
categories:
- retrogaming
- zx-spectrum
- reparation
date: "2026-05-05T00:00:00Z"
description: 
image: /post/images/zxspectrum2+128k.jpg
name: Youen Chene
title: ZX Spectrum 2+ 128k - Réparation du Son
url: /2026/05/05/ZX-Spectrum2-reparation-son
updated: "2026-05-05T00:00:00Z"
---

Après la réparation du clavier, voici un autre problème classique sur le ZX Spectrum 2+ 128k (modèle gris) : un problème de son.

![Photo d'un ZX Spectrum 2+ 128k](/post/images/zxspectrum2+128k.jpg)

## Diagnostic

Le son produit par l'ordinateur est très bruité et déséquilibré. C'est un problème connu sur les modèles 128K, +2 et +3, lié au circuit audio autour de la puce sonore AY-3-8912.

Voici un aperçu du son avant la réparation :

<video controls width="100%">
  <source src="/post/images/zx-sound-before.mp4" type="video/mp4">
</video>

De plus, j'utilise un câble péritel (SCART) d'excellente qualité de chez [RetroComputerShack](https://www.retrocomputershack.com/SCART-DESIGNS/Spectrum-128K/index.html). Sur ce modèle, le câble récupère le signal vidéo sur le port `PERITEL` et le son directement via une prise jack sur le port `SON` (Tape/Sound) pour une meilleure qualité.

![Câble péritel RetroComputerShack branché sur le ZX Spectrum](/post/images/zx-sound-issue-img-9514.jpg)

## Première tentative

### Résolution

La solution, [bien documentée en ligne](https://retrorepairsandrefurbs.com/2021/07/07/sinclair-zx-spectrum-128k2-grey-restoration/), consiste à remplacer plusieurs résistances par des valeurs différentes pour équilibrer correctement les différentes sources audio (EAR, MIC, et la puce AY).

Voici les modifications à apporter :

*   **R80** (Sortie audio EAR) : 10k sur le schéma d'origine, à remplacer par une résistance de **330k 0.5W**.
*   **R45** (Sortie audio MIC) : 10k sur le schéma d'origine, à remplacer par une résistance de **39k 0.5W**.
*   **R37** (Sortie audio de la puce AY) : 10k sur le schéma d'origine, à remplacer par une résistance de **3.3k 0.5W**.

*(Note : La résistance R38 pour la sortie audio RF n'a pas besoin d'être modifiée).*

Voici le schéma de la zone concernée :

![Schéma des résistances audio](/post/images/zx-sound-issue-2-audio.jpg)

Et voici les résistances remplacées sur la carte mère :

![Remplacement des résistances sur la carte mère](/post/images/zx-sound-issue-img-9511.jpg)


### Résultat

Après avoir remplacé ces trois résistances, on commence à entendre un peu de son mais le bruit de fonds est toujours super présent.


## Deuxième tentative

### Diagnostic

Pour isoler le problème, j'ai fait un test simple : lancer un jeu, puis débrancher la prise DIN vidéo. Et là, miracle : le son sortant sur mon enceinte externe (via la prise jack) est devenu parfaitement clair ! Le problème venait donc du câble vidéo ou de son interaction avec la carte mère.

### Résolution

Après une [discussion sur le forum Sinclair ZX World](https://www.sinclairzxworld.com/viewtopic.php?f=21&t=6090&p=60765#p60765), l'explication est en fait assez simple. 

Il s'avère qu'il y a une différence de câblage interne entre les modèles anglais et français du ZX Spectrum +2 gris au niveau de la prise vidéo (DIN) :
*   **Sur le modèle UK** : La broche 3 (Pin 3) correspond au signal "Bright Video Output".
*   **Sur le modèle Français** : La broche 3 correspond à la sortie audio ("Audio Sound Output").

Le câble péritel de chez [Retro Computer Shack](https://www.retrocomputershack.com/SCART-DESIGNS/Spectrum-128K/index.html) est conçu pour être compatible avec les modèles UK (Toastrack). Dans ce câble, le fil jaune relié à la broche 3 est connecté aux signaux vidéo RGB via des diodes. 

Conséquence sur un modèle français : le signal audio sortant de la broche 3 est injecté directement dans les lignes vidéo, ce qui crée cette horrible interférence sonore !

La solution est donc très simple : il suffit d'ouvrir la prise DIN du câble, de dessouder le fil jaune (Pin 3) et de l'isoler pour qu'il ne touche plus rien.

Voici le schéma de câblage du câble péritel (issu du site Retro Computer Shack) montrant ce fameux fil jaune sur la Pin 3 :

![Schéma de câblage du câble péritel Retro Computer Shack](/post/images/spectrum-128k-scart001008.jpg)

Et voici la modification à effectuer sur mon câble :

![Fil jaune à couper et isoler dans la prise DIN](/post/images/zx-sound-issue-img-9518.jpg)

### Résultat

Ça y est, le son est beaucoup plus clair et le bruit de fond a disparu.

Voici le résultat en vidéo :

<video controls width="100%">
  <source src="/post/images/zx-sound-after.mp4" type="video/mp4">
</video>

Et c'est reparti pour profiter des classiques du Spectrum dans de bonnes conditions sonores !
