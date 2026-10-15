% Copyright 2024 Caroline Blank <caro@c-space.org>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Exercices avec boucles for et while

## Exercice {num2}`exercice`

Cochez la bonne réponse.

```{defaults} quiz-check
:randomize:
:class: grid-4
```
{.lower-alpha-paren}
1.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog3.1
    :when:
    :linenos:
    x = 0
    while x < 4:
      print(x)
      x += 1
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog3.1
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 1
      while x < 4:
        print(x)
        x += 1
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 0
      while x <= 4:
        print(x)
        x += 1
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 1
      while x <= 4:
        print(x)
        x += 1
      ```
    ````
    `````
2.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog3.2
    :when:
    :linenos:
    x = 0
    while x < 4:
      x += 1
      print(x)
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog3.2
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 1
      while x < 4:
        x += 1
        print(x)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 0
      while x <= 4:
        x += 1
        print(x)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 1
      while x <= 4:
        x += 1
        print(x)
      ```
    ````
    `````
3.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog3.3
    :when:
    :linenos:
    x = 0
    while x <= 6:
      print(x)
      x += 2
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog3.3
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 1
      while x < 6:
        print(x)
        x += 2
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 0
      while x < 6:
        print(x)
        x += 1
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 1
      while x <= 6:
        print(x)
        x += 2
      ```
    ````
    `````
4.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog3.4
    :when:
    :linenos:
    x = 1
    while x < 6:
      x += 3
      print(x)
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog3.4
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 0
      while x < 6:
        x += 3
        print(x)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 0
      while x <= 6:
        x += 3
        print(x)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 1
      while x <= 6:
        x += 3
        print(x)
      ```
    ````
    `````
5.  Qu'affiche le progamme suivant?

    ```{exec} python
    :name: prog3.5
    :when:
    :linenos:
    x = 10
    while x >= 4:
      x -= 2
      print(x)
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :after: prog3.5
      :when: load
      :class: hidden
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 10
      while x > 4:
        x -= 1
        print(x)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 10
      while x > 4:
        x -= 2
        print(x)
      ```
    - ```{exec} python
      :when: load
      :class: hidden
      x = 11
      while x >= 4:
        x -= 2
        print(x)
      ```
    ````
    `````

## Exercice {num2}`exercice`

Il est toujours possible de convertir une boucle `for` en boucle `while`, par
contre il n'est pas toujours possible de convertir une boucle `while` en boucle
`for`, notamment si on ne sait pas à l'avance le nombre d'itérations.

```{defaults} quiz-check
:randomize:
:multi:
:class: grid-2
```

{.lower-alpha-paren}
1.  Quel(s) code(s) correspond(ent) à la boucle `for` ci-dessous?

    ```{exec} python
    :when:
    :linenos:
    for i in range(5):
      print(i)
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :when:
      :linenos:
      x = 0
      while x < 5:
        print(x)
        x += 1
      ```
    - ```{exec} python
      :when:
      :linenos:
      while x < 5:
        print(x)
      ```
    - ```{exec} python
      :when:
      x = 0
      while x < 6:
        print(x)
        x += 1
      ```
    - ```{exec} python
      :when:
      :linenos:
      x = 0
      while x < 5:
        x += 1
        print(x)
      ```
    ````
    ``````
2.  Quel(s) code(s) correspond(ent) à la boucle `for` ci-dessous?

    ```{exec} python
    :when:
    :linenos:
    for i in range(4):
      print(i + 1)
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :when:
      :linenos:
      x = 1
      while x < 5:
        print(x)
        x += 1
      ```
    - :
      ```{exec} python
      :when:
      :linenos:
      x = 0
      while x < 4:
        x += 1
        print(x)
      ```
    - ```{exec} python
      :when:
      x = 0
      while x < 5:
        print(x+1)
        x += 1
      ```
    - ```{exec} python
      :when:
      :linenos:
      x = 1
      while x < 5:
        print(x+1)
        x += 1
      ```
    ````
    `````
3.  Quel(s) code(s) correspond(ent) à la boucle `while` ci-dessous?

    ```{exec} python
    :when:
    :linenos:
    x = 4
    while x < 7:
      print(x)
      x += 1
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :when:
      :linenos:
      for i in range(4, 7):
        print(i)
      ```
    - :
      ```{exec} python
      :when:
      :linenos:
      for i in range(3):
        print(i + 4)
      ```
    - ```{exec} python
      :when:
      for i in range(3, 7):
        print(i)
      ```
    - ```{exec} python
      :when:
      :linenos:
      for i in range(4, 8):
        print(i)
      ```
    ````
    `````
4.  Quel(s) code(s) correspond(ent) à la boucle `while` ci-dessous?

    ```{exec} python
    :when:
    :linenos:
    x = 2
    while x <= 5:
      print(x)
      x += 1
    ```
    `````{quiz}
    ````{quiz-check}
    - :
      ```{exec} python
      :when:
      :linenos:
      for i in range(2, 6):
        print(i)
      ```
    - :
      ```{exec} python
      :when:
      :linenos:
      for i in range(1, 5):
        print(i + 1)
      ```
    - ```{exec} python
      :when:
      :linenos:
      for i in range(5):
        print(i)
      ```
    - ```{exec} python
      :when:
      :linenos:
      for i in range(2, 5):
        print(i)
      ```
    ````
    `````
5.  Cochez les boucles `while` qui ne peuvent pas être transformées en boucle
    `for`.

    `````{quiz}
    ````{quiz-check}
    :class: grid-1
    - :
      ```{exec} python
      :when:
      :linenos:
      n = int(input("Entrer un nombre strictement positif: "))
      while n <= 0:
        print("Le nombre doit être strictement positif!")
        n = int(input("Entrer un nombre strictement positif: "))
      print("Merci")
      ```
    - :
      ```{exec} python
      :when:
      :linenos:
      mot_de_passe = ""
      while mot_de_passe != "secret123":
          mot_de_passe = input("Entrez le mot de passe: ")
      print("Accès autorisé!")
      ```
    - ```{exec} python
      :when:
      :linenos:
      compte_a_rebours = 5
      while compte_a_rebours > 0:
        print(compte_a_rebours)
        compte_a_rebours -= 1
      print("Bonne année!")
      ```
    - :
      ```{exec} python
      :when:
      :linenos:
      nb_cantons = int(input("Combien y a-t-il de cantons en Suisse?"))
      while nb_cantons != 26:
        if nb_cantons < 26:
          nb_cantons = int(input("Faux, il y en a plus! Essaie encore."))
        else:
          nb_cantons = int(input("Faux, il y en a moins! Essaie encore."))
      print("Bravo!")
      ```
    - ```{exec} python
      :when:
      :linenos:
      x = 1
      n = 4
      while x <= 5:
        print(" _ " * n)
        print("|_|" * n)
        x += 1
      ```
    ````
    `````
## Exercice {num2}`exercice:py1-boom`

Nous souhaitons créer un programme qui compte le temps avant qu'une bombe
explose. Pour cela, un compte à rebours commencera à 10 et ira jusqu'à 1, puis
le programme affichera "BOOM".

Écrivez un programme qui correspond à l'algorithme suivant:

```{code-block} text
Initialiser une variable compte_a_rebours à 10
Tant que compte_a_rebours est plus grand que 0
    Afficher la valeur de compte_a_rebours
    Retirer 1 à compte_a_rebours
Afficher "BOOM"
```

Ce programme doit alors afficher:

```{code-block} text
10
9
8
7
6
5
4
3
2
1
BOOM
```

```{exec} python
:editor: fffa34af-43d1-40f0-ae0a-30c18ac2e5a0
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
compte_a_rebours = 10
while compte_a_rebours > 0:
  print(compte_a_rebours)
  compte_a_rebours -= 1
print("BOOM")
```

```{exec} python
:linenos:
for compte_a_rebours in range( 10,0, -1):
  print(compte_a_rebours)
print("BOOM")
```
````

## Exercice {num2}`exercice`

Reprenez l'{numref}`exercice %s<exercice:py1-boom>` ci-dessus et modifiez-le pour qu'à
partir de 3, il affiche également "Fuyez!".

```{code-block} text
10
9
...
4
3 Fuyez!
2 Fuyez!
1 Fuyez!
BOOM
```

```{exec} python
:editor: 7ff640be-fd71-493b-bb0c-f7c495af9ac2
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
compte_a_rebours = 10
while compte_a_rebours > 0:
  if compte_a_rebours <= 3:
    print(compte_a_rebours, "Fuyez!")
  else:
    print(compte_a_rebours)
  compte_a_rebours -= 1
print("BOOM")
```

```{exec} python
:linenos:
for compte_a_rebours in range( 10,0, -1):
  if compte_a_rebours <= 3:
    print(compte_a_rebours, "Fuyez!")
  else:
    print(compte_a_rebours)
print("BOOM")
```
````

## Exercice {num2}`exercice`

Écrivez un programme qui correspond à l'algorithme suivant:

Une boutique a initialement 200 produits en stock. Chaque jour, 40 produits sont
vendus.
- Affichez le nombre de produits restants chaque jour dans le format 
  *Jour x, produits en stock: y*  (les valeurs *x* et *y* étant modifiées chaque jour)
- Affichez "Stock épuisé!" lorsque tous les produits ont été vendus.


```{exec} python
:editor: 2e37947f-c6f8-456e-915e-f8c30b3678c2
# Écrivez le code ici...
```

````{solution}
```{exec} python
:linenos:
# Initialisation du nombre de produits en stock
produits_en_stock = 200
jour = 0

# Tant qu'il y a des produits en stock
while produits_en_stock > 0:
    
    # incrémentation du jour
    jour += 1
	
    # Réduire le stock de 40 produits chaque jour
    produits_en_stock -= 40

    # Afficher le nombre de produits restants
    print("Jour", jour, ", produits en stocks: ", produits_en_stock)

# Afficher que le stock est épuisé une fois que la boucle est terminée
print("Stock épuisé après ", jour, "jours!")
```
````

## Exercice {num2}`exercice`

Bob souhaite construire une pyramide à base carrée comme sur la photo.

```{figure} images/pyramide.png
:alt: Pyramide
:width: 200px
:align: center
```
{.lower-alpha-paren}
1.  Écrivez un programme qui permet de calculer le nombre de billes nécessaires
    pour construire la pyramide de l'image (elle a 7 étages). Utilisez une
    boucle `for`.

    ```{exec} python
    :editor: e71a7353-1236-4047-8c5b-2dcd42017bfa
    # Écrivez le programme ici
    ```

    ````{solution}
    ```{exec} python
    :linenos:
    nb_billes = 0
    for i in range(7):
      nb_billes += (i + 1) ** 2
    print(nb_billes)
    ```

    ```{exec} python
    :linenos:
    nb_billes = 0
    for etage in range(1, 8):
      nb_billes += etage ** 2
    print(nb_billes)
    ```
    ````

2.  Modifiez le programme précédent pour calculer le nombre de billes
    nécessaires pour construire une pyramide à 100 étages.

    ```{exec} python
    :editor: 277cfc59-fcf8-4667-a845-01585976347c
    # Écrivez le programme ici
    ```

    ````{solution}
    ```{exec} python
    :linenos:
    nb_billes = 0
    for i in range(100):
      nb_billes += (i + 1) ** 2
    print(nb_billes)
    ```

    ```{exec} python
    :linenos:
    nb_billes = 0
    for etage in range(1, 101):
      nb_billes += etage ** 2
    print(nb_billes)
    ```
    ````

3.  Modifiez le programme pour que l'utilisateur puisse choisir le nombre
    d'étages.

    ```{exec} python
    :editor: 6c6da905-b3ad-4971-9ac0-705facf2a1e9
    # Écrivez le programme ici
    ```

    ````{solution}
    ```{exec} python
    :linenos:
    nb_etages = int(input("Choisissez le nombre d'étages: "))
    nb_billes = 0
    for i in range(nb_etages):
      nb_billes += (i + 1) ** 2
    print(nb_billes)
    ```

    ```{exec} python
    :linenos:
    nb_etages = int(input("Choisissez le nombre d'étages: "))
    nb_billes = 0
    for etage in range(1, nb_etages + 1):
      nb_billes += etage ** 2
    print(nb_billes)
    ```
    ````