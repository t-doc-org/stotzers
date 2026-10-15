% Copyright 2024 Caroline Blank <caro@c-space.org>
% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Boucle for

## Répétition d'un bloc d'instructions

La boucle `for` permet de répéter un bloc d'instructions un nombre de fois connu
à l'avance.

```{exec} python
:when:
for _ in range(nb_repetitions):
  instruction 1
  instruction 2
  ...
```

```{important}
En Python, les instructions appartenant à un même **bloc d'instructions** sont reconnaissables car elles ont toutes exactement la même **indentation**.
```

### Exemple {num2}`exemple`

````{list-grid}
:style: grid-template-columns: 1fr 1fr;
- # Programme
  ```{exec} python
  :editor:
  print("Voici ma punition:")
  for _ in range(10):
    print("Je dois faire mes devoirs.")
  print("J'ai fini.")
  ```
- # Ordinogramme
  ```{figure} images/boucle-for.png
  :alt: Ordinogramme boucle for
  ```
````

### Exercice {num2}`exercice`

`````{tab-set}
:sync-group: etape
````{tab-item} Étape 1
:sync: etape1
Que fait le programme suivant?
````

````{tab-item} Étape 2
:sync: etape2
Modifiez-le pour qu'il affiche 9 fois "Salut".
````

````{tab-item} Étape 3
:sync: etape3
Modifiez-le pour qu'il affiche:
```{code-block} text
Salut
Comment ça va?
Salut
Comment ça va?
Salut
Comment ça va?
```
````

````{tab-item} Étape 4
:sync: etape4
Modifiez-le pour qu'à la fin du programme, il affiche "Au revoir!".
````

`````

```{exec} python
:editor: cdf06593-2fc5-4f68-af74-2a6113bec6dc
for _ in range(6):
  print("Salut")
```

````{solution}
```{exec} python
:linenos:
for _ in range(3):
  print("Salut")
  print("Comment ça va?")
print("Au revoir!")
```
````

## Utilisation de la variable de la boucle for

La boucle `for` fait plus que juste répéter x fois un bloc d'instructions: pour
chaque itération (passage dans la boucle), la variable (dans l'exemple ci-dessous
nommée `i`) va prendre la valeur de l'ensemble `range(n)`, c'est-à-dire
l'ensemble des nombres entiers de $0$ à $n$ non compris $\{0; 1; 2; ...; n-1\}$.
Il est donc possible d'utiliser la valeur de cette variable dans la boucle.

```{important}
Dans l'instruction `for _ in range(nb_repetitions):`, le `_` représente une variable à laquelle nous n'avons pas donné de nom. Mais il est possible de donner un nom (en respectant les règles de nommage des variables) si nous avons besoin d'utiliser cette variable dans le bloc d'instructions.

Toutes ces notations sont correctes: 

- `for _ in range(3):`
- `for nombre in range(3):`
- `for i in range(3):`

La syntaxe `for _ in range(3):` est utilisée seulement lorsque nous n'utilisons pas la
valeur de la variable dans la boucle (on dit que c'est une **variable muette**)
```

### Exemple {num2}`exemple`

Le programme suivant affiche les nombres de 0 à 9.

```{exec} python
:editor:
for i in range(10):
  print(i)
```

### Exercice {num2}`exercice`

Écrivez un programme qui affiche les nombres entiers de 0 jusqu'à 17 et affiche
à la fin "J'ai fini de compter!".

```{exec} python
:editor: d9ce7741-30c3-4891-a481-0f84f99d4e9f
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
for nombre in range(18):
  print(nombre)
print("J'ai fini de compter!")
```
````

### Exercice {num2}`exercice`

Modifiez le programme ci-dessous pour qu'il affiche les nombres entiers de 1 à
10.

```{exec} python
:editor: f0af01c7-fee8-47ef-bd3a-7ff011012f27
for i in range(10):
  print(i)
```

````{solution}
```{exec} python
:linenos:
for i in range(10):
  print(i + 1)
```

Python permet aussi de déterminer la valeur de départ et la valeur de fin (pas
comprise), en utilisant le construction suivante:
```{exec} python
:linenos:
for i in range(1, 11):
  print(i)
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui calcule et affiche la somme des dix premiers nombres
entiers plus grands que 0.

```{exec} python
:editor: 861f4829-841e-48f7-8597-91d4153f3cde
# Écrivez le programme ici
```

````{solution}

Il y a plusieurs manières de faire.

{.lower-alpha-paren}
1.  Comme ajouter 0 à une somme ne change rien, je peux effectuer le calcul
    suivant: $0 + 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10$

    ```{exec} python
    :linenos:
    somme = 0
    for i in range(11):
      somme += i
    print(somme)
    ```

2.  Les deux programmes suivants font exactement ce qu'il faut:
    $1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10$

    ```{exec} python
    :linenos:
    somme = 0
    for i in range(10):
      somme += i + 1
    print(somme)
    ```

    ```{exec} python
    :linenos:
    somme = 0
    for i in range(1, 11):
      somme += i
    print(somme)
    ```
````

### Exercice {num2}`exercice`

Écrivez un programme qui calcule et affiche le produit des cinq premiers nombres
entiers plus grands que 0.

```{exec} python
:editor: 165c348a-10cd-4161-8ff4-d95acfbf7e25
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
produit = 1
for i in range(5):
  produit *= i + 1
print(produit)
```

```{exec} python
:linenos:
produit = 1
for i in range(1, 6):
  produit *= i
print(produit)
```
````

## L'instruction range()
L’instruction `for … in` permet de parcourir tous les éléments d’une suite d’éléments définie avec la fonction `range()`. Cette fonction `range()` peut prendre 1, 2 ou 3 paramètres 

- `range(n)`: parcourt tous les éléments de `0` à `n-1`
  - Exemple: `range(5)` parcourra tous les éléments de la liste [0, 1, 2, 3, 4]

- `range(a, n)`: parcourt tous les éléments de `a` à `n-1`
  - Exemple: `range(36,40)` parcourra tous les éléments de la liste [36, 37, 38, 39]

- `range(a, n ,p)` parcourt tous les éléments de `a` à `n-1` avec un pas de `p`. 

  - Exemple: `range(10,18,2)` parcourra tous les éléments de la liste [10, 12, 14, 16]
  - Exemple: `range(10,0,-2)` parcourra tous les éléments de la liste [10, 8, 6, 4, 2]

Remarques: 
  - `a`, `n` et `p` doivent être des nombres entiers (integer)
  - Si la valeur de début est plus grande que la valeur de fin, alors le pas `p` doit être positif.
  - Si la valeur de début est plus petite que la valeur de fin, alors le pas `p` doit être négatif.


### Exemple {num2}`exemple`
Modifiez les paramètres `a`, `n` et `p` dans l'exemple ci-dessous afin de voir quelles sont les valeurs qui seront parcourures par la variable `i` dans la boucle `for()`
  ```{exec} python
  :editor:
  # Modifiez les paramètres `a`, `n` et `p` ci-dessous
  a = 1	    # valeur de début
  n = 10    # valeur de fin
  p = 2	    # pas
  
  print("range(", a ,",", n ,",", p ,"): ")
  for i in range(a, n ,p):
    print(i)
  ```

### Exercice {num2}`exercice`

Cochez la bonne réponse.

```{defaults} quiz-check
:randomize:
:class: grid-4
```

{.lower-alpha-paren}
1.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog6.1
    :when:
    :linenos:
    for i in range(3):
      print("Hello")
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog6.1
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(3):
        print(i)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(2):
        print("Hello")
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(4):
        print("Hello")
      ```
    ````
	`````
2.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog6.2
    :when:
    :linenos:
    for i in range(4):
      print(i)
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog6.2
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(4):
        print(i+1)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(5):
        print(i)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(4):
        print("4")
      ```
    ````
    `````
3.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog6.3
    :when:
    :linenos:
    for i in range(2):
      print("i")
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog6.3
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(2):
        print(i)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(3):
        print(i)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(1):
        print(i)
      ```
    ````
    `````
4.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog6.4
    :when:
    :linenos:
    for i in range(3, 7):
      print(i+1)
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog6.4
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(2, 6):
        print(i+1)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(3, 7):
        print(i+1)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      print(3)
	  print(7)
      ```
    ````
    `````
5.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog6.5
    :when:
    :linenos:
    for i in range(5,20,3):
      print(i)
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog6.5
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(5,21,3):
        print(i)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      for i in range(3,21,5):
        print(i)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      print(5)
      print(20)
      print(3)
      ```
    ````
    `````
	
### Exercice {num2}`exercice`

Écrivez un programme qui demande à l'utilisateur un nombre entier positif et
affiche les 10 premiers multiples de ce nombre.

```{exec} python
:editor: f935054b-3ed6-4a42-9e73-e6330a770f1d
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
nombre = int(input("Choisissez un nombre: "))
for i in range(10):
  print(nombre * (i + 1))
```

```{exec} python
:linenos:
nombre = int(input("Choisissez un nombre: "))
for i in range(1, 11):
  print(nombre * i)
```

```{exec} python
:linenos:
nombre = int(input("Choisissez un nombre: "))
for i in range(nombre, 10*nombre, nombre+1):
  print(i)
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui affiche les nombres pairs jusqu'à 20.

```{exec} python
:editor: c0a8317f-b8d9-465b-85f6-2865f32d4d6e
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
# parcourt tous les nombres de 2 à 20 en faisant à chaque fois un pas de 2
for i in range(2, 21, 2):
  print(i)
```

```{exec} python
:linenos:
# parcourt tous les nombres de 1 à 20 et n'affiche que les nombres pairs
for i in range(1, 21):
  if i % 2 == 0:
    print(i)
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui affiche le résultat des calculs suivants sans le noter
explicitement:

{.lower-alpha-paren}
1.  $1 + 2 + 3 + 4 + ... + 99 + 100$

    ```{exec} python
    :editor: f281c8dd-259a-431c-8a7b-f72732aee8db
    # Écrivez le programme ici
    ```

    ````{solution}
    ```{exec} python
    :linenos:
    somme = 0
    for i in range(100):
      somme += i + 1
    print(somme)
    ```

    ```{exec} python
    :linenos:
    somme = 0
    for i in range(1, 101):
      somme += i
    print(somme)
    ```
    ````

2.  $1 + 3 + 5 + 7 + ... + 97 + 99$

    ```{exec} python
    :editor: 6d671b57-eff1-474e-8fed-4f8ddbb5595d
    # Écrivez le programme ici
    ```

    ````{solution}
    ```{exec} python
    :linenos:
    somme = 0
    for i in range(100):
      if (i + 1) % 2 == 1:
        somme += i + 1
    print(somme)
    ```

    ```{exec} python
    :linenos:
    somme = 0
    for i in range(1, 101):
      if i % 2 == 1:
        somme += i
    print(somme)
    ```
    ````


### Exercice {num2}`exercice`

Ecrivez un programme qui permette de dessiner un sapin comme sur le modèle ci-dessous.

```{figure} images/sapin.png
:alt: Pyramide
:width: 200px
:align: center
```
- Pour ceci, le programme doit demander à l'utilisateur la hauteur du sapin (c'est-à-dire le nombre de lignes de 'O'). Le dessin ci-dessus est a une hauteur de 7. 
- Dessinez à la main un petit sapin afin de déterminer le nombre d'espaces et le nombre de 'O' à dessiner pour chacune des lignes
- créez une boucle qui pour à chaque passage dessinera une ligne du dessin: un certain nombre d'espaces suivi d'un certain nombre de 'O'
- Pour équilibrer le tout, il faut dessiner un tronc: la hauteur du tronc correspond au tiers de la hauteur du sapin (utiliser pour ceci la division entière)


```{exec} python
:editor: 6c6da005-b3ad-4971-9ac0-705facf2a1e9
# Écrivez le programme ici
```

````{tip}
Par défaut, la fonction `print()` ajoute automatiquement un retour à la ligne comme dernier caractère.
Pour ne pas avoir de retour à la ligne, il est possible de redéfinir (et de le remplacer par un caractère vide) en ajoutant `end=""` comme dernier argument:  
```{exec} python
:linenos:
print("a")
print("b")
print("c")
print("d", end="")
print("e", end="")
print("f")
```
````