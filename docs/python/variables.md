% Copyright 2024 Caroline Blank <caro@c-space.org>
% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Variables

## Définition

Nous pouvons nous représenter une variable comme l'association d'une étiquette
(nom de la variable) et d'une case pouvant contenir une donnée (emplacement
dans la mémoire).

```{image} images/boites.png
:alt: Boites de variables
:width: 50%
:align: center
```

Une variable permet de stocker une valeur numérique, une chaîne de caractères,
etc. qu'on réutilisera par la suite dans notre programme. Pour un programmeur,
une variable est définie par un **nom**. Mais pour l'ordinateur, il
s'agit d'une adresse (emplacement de la mémoire où est stockée cette donnée).

```{attention}
Règles à respecter:

- Le nom de la variable doit correspondre à son contenu.\
  Exemple: age, hauteur
- Le caractère \_ permet de séparer les mots dans un nom de variable.\
  Exemple: cote_carre
- Le nom d'une variable ne doit pas contenir de caractère accentué.
- Le nom d'une variable doit commencer par une lettre ou le caractère de
  soulignement.
- Le nom d'une variable ne peut contenir que les caractères alphanumériques
  (A-z 0-9 et \_)
- Les majuscules et les minuscules font une différence.
  Exemple: mon\_age, mon\_Age, mon\_AGE sont trois variables différentes
```

## Types de données

En Python, il existe 4 types de données primitifs.

| Type      | Nom       | Description                      | Exemple            |
|---------  |--------   |----------------------------------|--------------------|
| **int**   | integer   | Nombres entiers                  | 4                  |
| **float** | flottant  | Nombres à virgules               | 4.125              |
| **str**   | string    | Chaînes de caractères            | "Bonjour"          |
| **bool**  | booléen   | Résultat d'un test: Vrai (**True**) ou Faux (**False** ) | 2<1 renvoie False  |

### Exercice {num2}`exercice`

De quel type sont les valeurs suivantes?

```{role} select(quiz-select)
:right:
:options: |
: int
: float
: str
: bool
```

```{quiz}
:style: max-width: 20rem;
1.  {select}`int`   `60`
2.  {select}`str`   `"Hello Bob"`
3.  {select}`float` `1.34`
4.  {select}`bool`  `True`
5.  {select}`str`   `"45"`
6.  {select}`float` `-1.23`
7.  {select}`str`   `"False"`
8.  {select}`float` `0.34`
9.  {select}`int`   `-12`
10. {select}`bool`  `False`
```

## Affectation d'une variable

**L'affectation d'une variable** est l'opération qui consiste à donner une valeur à une variable.

L'affectation d'une variable se fait au moyen du nom de la variable, suivi du signe `=`
et de la valeur.

```{exec} python
:linenos:
:when:
age = 17                  # La variable age est de type int
prenom = "Bob"            # La variable prenom est de type str
moyenne = 5.2             # La variable moyenne est de type float
promu = True              # La variable promu est de type bool
```

```{attention}
Il ne faut pas confondre les opérateurs `==` et `=`:

- `==` est une comparaison entre 2 valeurs. Il peut être compris comme une question: est-ce que la valeur à gauche de l'opérateur `==` est égale celle qui est à droite?
- `=` est l'affectation d'une variable: la variable qui se trouve à gauche de l'opérateur `=` prendra la valeur qui se trouve à droite.
```

### Exercice {num2}`exercice`

Ce programme Python déclare 5 variables, mais contient une erreur par ligne.
Trouvez et corrigez-les.

```{exec} python
:editor:
6 = age
message = Je suis absent
note = 4,5
porte_ouverte = false
nombre de voitures = 10
```

````{solution}
```{exec} python
:linenos:
age = 6
message = "Je suis absent"
note = 4.5
porte_ouverte = False
nombre_de_voitures = 10
```

1.  À la création d'une variable, le nom doit toujours être à gauche du signe
    égal, et la valeur à droite.
2.  Une valeur de type `str` doit être entourée de guillemets.
3.  Une valeur de type `float` s'écrit non pas avec une virgule mais avec un
    point.
4.  Une valeur de type `bool` prend une majuscule à `True` et `False`.
5.  Les noms de variables ne peuvent pas contenir d'espaces. Généralement, en
    Python, on les remplace alors par le caractère de soulignement.
````

## Exécution d'un programme

Lors de l'exécution d'un programme, Python va lire les instructions ligne par
ligne et les effectuer. Afin de comprendre comment fonctionne un programme et
évaluer le résultat, nous allons utiliser des tableaux d'états. Ceux-ci
permettent de connaître à chaque ligne, la valeur des variables.

### Exemple {num2}`exemple`

````{list-grid}
:style: grid-template-columns: 1fr min-content;
- # Programme
  ```{exec} python
  :linenos:
  a = 10
  b = 30
  c = a + b
  d = c * a
  a = 2 * a

  # Affiche les valeurs des variables
  print(a, b, c, d)
  ```
- # Tableau d'états
  | ligne | a | b | c | d |
  |:-----:|:-:|:-:|:-:|:-:|
  | 1 | 10| ? | ? | ? |
  | 2 | 10| 30| ? | ? |
  | 3 | 10| 30| 40| ? |
  | 4 | 10| 30| 40| 400|
  | 5 | 20| 30| 40| 400|
````

### Exercice {num2}`exercice`

Déterminez la valeur de chacune des variables de ce programme en créant un
tableau d'états.

```{exec} python
:linenos:
:when:
x = 10
y = 2
z = y * x
y = z + x
x = y - z / 2
z = z * 2
y = 5

# Affiche les valeurs des variables
print(x, y, z)
```

`````{solution}
````{list-grid}
:style: grid-template-columns: 1fr min-content;
- ```{exec} python
  :linenos:
  x = 10
  y = 2
  z = y * x
  y = z + x
  x = y - z / 2
  z = z * 2
  y = 5

  # Affiche les valeurs des variables
  print(x, y, z)
  ```
- | ligne | x  | y  | z  |
  |:-----:| :-:| :-:| :-:|
  | 1 | 10 | ?  | ?  |
  | 2 | 10 | 2  | ?  |
  | 3 | 10 | 2  | 20 |
  | 4 | 10 | 30 | 20 |
  | 5 | 20 | 30 | 20 |
  | 6 | 20 | 30 | 40 |
  | 7 | 20 | 5  | 40 |
````
`````

### Exercice {num2}`exercice`

Déterminez la valeur de chacune des variables de ce programme en créant un
tableau d'états.

```{exec} python
:linenos:
:when:
nombre_habitants = 150 + 25 * 2
cout = 100
prix = nombre_habitants * cout
cout = cout / 2
nombre_habitants = nombre_habitants - 100
prix = prix + nombre_habitants * cout
nombre_habitants = 400
prix = prix + nombre_habitants * cout

# Affiche les valeurs des variables
print(nombre_habitants, cout, prix)
```

````{solution}
```{exec} python
:linenos:
nombre_habitants = 150 + 25 * 2
cout = 100
prix = nombre_habitants * cout
cout = cout / 2
nombre_habitants = nombre_habitants - 100
prix = prix + nombre_habitants * cout
nombre_habitants = 400
prix = prix + nombre_habitants * cout

# Affiche les valeurs des variables
print(nombre_habitants, cout, prix)
```

| ligne | nombre_habitants  | cout  | prix  |
|:-----:| :--| :--| :--|
| 1 | 200 |  ? | ?  |
| 2 | 200 | 100  | ? |
| 3 | 200 | 100  | 20000 |
| 4 | 200 | 50 | 20000 |
| 5 | 100 | 50 | 20000 |
| 6 | 100 | 50 | 25000 |
| 7 | 400 | 50  | 25000 |
| 8 | 400 | 50  | 45000 |

````

### Exercice {num2}`exercice`

Complétez le programme ci-dessous de manière à ce qu'il calcule la moyenne des
notes principales dans la variable du même nom. La note de math est de 4 et
demi, la note de français de 6 et la note d'allemand de 5 et demi.

```{exec} python
:editor: 184beb38-78ed-48e5-89ee-2c19101727fd
# Complétez le programme
math =
francais =
allemand =
moyenne =

# Affiche la valeur de la moyenne
print(moyenne)
```

````{solution}
```{exec} python
:linenos:
math = 4.5
francais = 6
allemand = 5.5
moyenne = (math + francais + allemand) / 3

# Affiche la valeur de la moyenne
print(moyenne)
```
Pour calculer la moyenne, on additionne toutes les notes avant de diviser le
résultat par le nombre de notes, ici 3.

Comme la division a la priorité sur l'addition, il ne faut pas oublier de
régler la priorité des opérations avec des parenthèses.
````

### Exercice {num2}`exercice`
Écrivez un petit programme en Python permettant de calculer le volume d'un
cylindre en fonction de son rayon et de sa hauteur. Le programme contiendra les
lignes suivantes :

-   Créer une variable `pi` contenant la valeur `3.14`.

-   Créer une variable `hauteur` contenant la valeur `30`

-   Créer une variable `rayon` contenant la moitié de 11

-   Créer une variable `aire_disque` contenant le résultat de
    $\pi \cdot r^2$

-   Créer une variable `volume` contenant le résultat de l'aire du
    disque multiplié par la hauteur.

Au terme de l'exécution de ce programme, la variable `volume` devrait
contenir la valeur `2849.55`

```{exec} python
:editor: 
# Écrivez le programme ici

# Affiche le volume
print(volume)
```

````{solution}
```{exec} python
:linenos:
pi = 3.14
hauteur = 30
rayon = 11 / 2 #ou rayon = 5.5
aire_disque = pi * rayon ** 2
volume = aire_disque * hauteur

# Affiche le volume
print(volume)
```
````
### Exercice {num2}`exercice`
On définit deux variables : `a=10` et `b=3`. Parmi les 4 programmes suivants, lesquels permettent
d’échanger le contenu des deux variables, de sorte qu’à la fin de l’exécution on obtienne `a: 3` et `b: 10` ?

`````{tab-set}
:sync-group: etape
````{tab-item} Programme 1
```{exec} python
:linenos:
:when:
# Programme 1
a = 10
b = 3

a = b
b = a

print("a: ", a)
print("b: ", b)
```
````

````{tab-item} Programme 2
```{exec} python
:linenos:
:when:
# Programme 2
a = 10
b = 3

c = b
a = b
b = c

print("a: ", a)
print("b: ", b)
```
````

````{tab-item} Programme 3
```{exec} python
:linenos:
:when:
# Programme 3
a = 10
b = 3

c = a
a = b
b = c

print("a: ", a)
print("b: ", b)
```
````

````{tab-item} Programme 4
```{exec} python
:linenos:
:when:
# Programme 4
a = 10
b = 3

a = a+b
b = a-b
a = a-b

print("a: ", a)
print("b: ", b)
```
`````

Vérifier vos réponse au moyen de la console ci-dessous:
```{exec} python
:editor: 
# Copiez le programme ici
```
### Exercice {num2}`exercice`
Les 3 programmes suivants  provoquent une erreur lors de l'exécution. Analysez ces programmes afin de retrouvez ces erreurs, puis corrigez-les (dans la mesure du possible).
1.  ```{exec} python
    :editor:
    base = 5
	hauteur = 6
	Aire = base* hauteur
	print(aire)
    ```

2.  ```{exec} python
    :editor:
    v = w+5
	w = 10
	print(v,w)
    ```

3.  ```{exec} python
    :editor:
    a = 10
	b = 0
	a = a**2
	b = a/b
	print(b)
    ```
	
## Opérateurs d'affectation

Les opérateurs d'affectation combinée permettent de modifier la valeur des
variables avec une notation simplifiée. Il en existe pour tous les opérateurs
mathématiques, voici les principaux.

| Opérateur | Exemple | Équivalent à |
| :-------: | :-----: | :----------: |
| =         | x = 6   | x = 6        |
| +=        | x += 6  | x = x + 6    |
| -=        | x -= 6  | x = x - 6    |
| \*=       | x \*= 6 | x = x * 6    |
| /=        | x /= 6  | x = x / 6    |

### Exercice {num2}`exercice`

Écrivez un programme Python contenant une variable `x` initialisée à 10.
Puis, complétez ce programme pour que celui-ci effectue les opérations
suivantes en utilisant les opérateurs d'affectation combinée:

-   Ajoute 3 à `x`

-   Soustrais 8 à `x`

-   Multiplie `x` par 10

-   Divise `x` par 5

-   Élève `x` à la puissance 3

À la fin de l'exécution de ce programme, la variable `x` devrait contenir la
valeur `1000`

```{exec} python
:editor: df136ddf-cd4a-4044-88f0-b061f0568d69
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
x = 10
x += 3
x -= 8
x *= 10
x /= 5
x **= 3

print(x)
```
````

### Exercice {num2}`exercice`

Lisez attentivement le programme ci-dessous et expliquez, en français, ce qu'il
fait. À quoi correspondent les variables `h_n`, `h_s`, et `total`?

```{exec} python
:linenos:
CHF_par_h_n = 30
CHF_par_h_s = 40
temps_de_travail = 10
h_s = temps_de_travail % 8
h_n = temps_de_travail - h_s
total = (h_n * CHF_par_h_n) + (h_s * CHF_par_h_s)
print(total)
```

```{solution}
:class: note dropdown
Ce programme permet de calculer et stocker le salaire d'un employé dans la
variable `total`. Les 8 premières heures (`h_n`) sont payées au tarif normal ( `CHF_par_h_n` ), 
et les heures supplémentaires (`h_s`) sont payés au tarif des heures supplémentaires ( `CHF_par_h_s` ).
```
