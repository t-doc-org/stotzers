% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Algorithme

## Définition

Un **algorithme** est une suite finie d'opérations non-ambigües permettant de résoudre un
problème. 

Un bon algorithme doit notamment être :

- clair et précis : il ne doit pas y avoir d'ambiguïté ;
- ordonné : les étapes sont exécutées dans un certain ordre ;
- fini : il doit arriver à un résultat après un nombre fini d'étapes.

Le mot *algorithme* provient de la forme latine (*Algorismus*) du nom du
mathématicien persan Al Khwarizmi qui a vécu au IXe siècle. Mais les premiers
algorithmes remontent aux Babyloniens (-3000 avant JC), avec notamment
l'algorithme d'Euclide qui permet de déterminer le plus grand diviseur commun de
deux nombres entiers.

```{youtube} iQpsPVVppZM
:title: Vidéo: Qu'est-ce qu'un algorithme
```


## Exemples

Il existe différents exemples d'algorithmes:
- une recette de cuisine
- un itinéraire routier
- une notice de montage d'un meuble en kit
- le brossage des dents
- en mathématiques : résoudre une équation du deuxième degré, déterminer si
  un nombre est premier, etc.

````{list-grid}
:style: grid-template-columns: 1fr 1fr;
- ```{image} images/laver_les_dents.jpg
	:alt: Algorithme pour le brossage des dents
	:width: 60%
	:align: center
	```
- ```{image} images/itineraire.png
	:alt: Itinéraire routier
	:width: 100%
	:align: center
	```
````

### Exercice {nump}`exercice`

```{image} images/algo-chien-1.png
:alt: Algorithme du chien 1
:width: 30%
:align: center
```

1. Aidez le chien à rejoindre sa niche en utilisant les flèches: &#x2190;,
&#x2192;,  &#x2191; et &#x2193;.

  ```{solution}
  &#x2192; &#x2192; &#x2193; &#x2192; &#x2192; &#x2192;
  ```

2. Aidez le chien à rejoindre sa niche en écrivant un algorithme avec des mots.

  ```{solution}
  Avancer, avancer, tourner à droite, avancer, tourner à gauche, avancer,
  avancer et avancer.
  ```

3. Y a-t-il des répétitions dans ton algorithme? Si oui, essayez de formuler
autrement pour les éviter.

  ```{solution}
  Avancer 2 fois, tourner à droite, avancer, tourner à gauche, avancer 3 fois.
  ```

### Exercice {nump}`exercice`

```{image} images/algo-chien-2.png
:alt: Algorithme du chien 2
:width: 40%
:align: center
```

1. Aidez le chien à ramasser tous les os et à rejoindre sa niche en utilisant
les flèches: &#x2190;, &#x2192;,  &#x2191; et &#x2193;.

  ```{solution}
  &#x2192; &#x2192; &#x2193; &#x2192; &#x2192; &#x2192; &#x2190; &#x2190;
  &#x2190; &#x2193; &#x2193; &#x2190; &#x2192; &#x2192; &#x2192; &#x2192;
  &#x2192;
  ```


2. Aidez le chien à ramasser tous les os et à rejoindre sa niche avec des mots
et sans répétition.

  ```{solution}
  Avancer 2 fois, ramasser l'os, tourner à droite, avancer, tourner à gauche,
  avancer 3 fois, ramasser l'os, reculer 3 fois, tourner à droite, avancer 2
  fois, tourner à droite, avancer, ramasser l'os, reculer 5 fois.
  ```

### Exercice {nump}`exercice`

```{image} images/algo-chien-3.png
:alt: Algorithme du chien 3
:width: 50%
:align: center
```

1. Aidez le chien à rejoindre sa niche en utilisant les flèches: &#x2190;,
&#x2192;,  &#x2191; et &#x2193;.

  ```{solution}
  &#x2192; &#x2193; &#x2193; &#x2192; &#x2193; &#x2193; &#x2192; &#x2193;
  &#x2193; &#x2192; &#x2192; &#x2192; &#x2192; &#x2192; &#x2192;
  ```

2. Aidez le chien à rejoindre sa niche avec des mots et sans répétition.

  ```{solution}
  Faire 3 fois: avancer, tourner à droite, avancer 2 fois, tourner à gauche\
  Avancer 6 fois
  ```

### Exercice {nump}`exercice`

```{image} images/algo-chien-4.png
:alt: Algorithme du chien 4
:width: 35%
:align: center
```

Aidez le chien à rejoindre sa niche avec des mots et sans répétition.

```{solution}
Faire 6 fois: avancer tant que possible et tourner à droite.
```

## Du problème à la résolution

Pour résoudre un problème au moyen d'un programme informatique, il y a
différentes étapes à suivre :

1. Comprendre et analyser le problème (être capable de l'expliquer)
2. Écrire un algorithme qui résout le problème
3. Programmer l'algorithme dans le langage choisi (pour nous ce sera Python)
4. Exécuter le programme pour obtenir le résultat
5. Tester différents scénarios afin de vérfifier que le programme ne comporte pas d'erreur


 ### Exercice {nump}`exercice`
 
 Appliquez différentes mécaniques de base de l'algorithmique et de la programmation dans le jeu [little-dot]( https://little-dot.toxicode.fr/)?
