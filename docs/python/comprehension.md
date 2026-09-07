% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.3

# Compréhension de code

## Notion de variable

### Exercice {nump}`exercice`

Sans l'exécuter, qu'affiche ce programme si:

1. `nombre_km = 55`?
2. `nombre_km = 45`?
3. `nombre_km = 50`?

Ensuite, exécutez le programme pour vérifier votre réponse.

```{exec} python
:editor:
nombre_km = ...
if nombre_km <= 50:
  prix_location = 100 + nombre_km * 0.5
else:
   prix_location = 100 + nombre_km * 0.4
print(nombre_km, prix_location)
```

```{solution}
1. 55 122 (passage dans le else)
2. 45 122.5 (passage dans le if)
3. 50 125 (passage dans le if)
```

### Exercice {nump}`exercice`

Sans exécuter le programme, répondez aux questions.

1. Quelle est la valeur stockée dans la variable `n` à la fin du programme?
2. Qu'est-ce que le programme affiche?

Ensuite, exécutez le programme pour vérifier vos réponses.

```{exec} python
:editor:
n = 4
for _ in range(3):
  n = n + 5
print(n+1)
```

```{solution}
1. n = 19
2. 20
```

### Exercice {nump}`exercice`

Sans l'exécuter, qu'est-ce que le programme suivant affiche.

Ensuite, exécutez le programme pour vérifier votre réponse.

```{exec} python
:editor:
n = 6
n *= 3
for _ in range(4):
  n = n + 2
  n = n / 2
n = n - 5
print(n)
```

```{solution}
-2.0
```

### Exercice {nump}`exercice` (boucle while)

Sans l'exécuter, qu'affiche ce programme:

1. si `n = 0`?
2. si `n = 5`?
3. si `n = 9`?

Ensuite, exécutez le programme avec ces différentes valeurs de `n` pour vérifier vos réponses.

```{exec} python
:editor:
n = ...
while n <= 5:
  print(n)
  n = n + 1
```

```{solution}
1. 0\
   1\
   2\
   3\
   4\
   5
2. 5x§
3. /
```

### Exercice {nump}`exercice` (boucle while)

Sans l'exécuter, qu'affiche ce programme si:

1. si `n = 0`?
2. si `n = 5`?
3. si `n = 9`?

Ensuite, exécutez le programme avec ces différentes valeurs de `n` pour vérifier vos réponses.

```{exec} python
:editor:
n = ...
while n <= 5:
  n = n + 1
  print(n)
```

```{solution}
1. 1\
   2\
   3\
   4\
   5\
   6
2. 6
3. /
```

### Exercice {nump}`exercice` (boucle while)

Sans l'exécuter, qu'affiche ce programme si:

1. si `n = 0`?
2. si `n = 5`?
3. si `n = 9`?

Ensuite, exécutez le programme pour vérifier votre réponse.

```{exec} python
:editor:
n = ...
while n <= 5:
  n = n + 1
print(n)
```

```{solution}
1. 6
2. 6
3. 9
```

### Exercice {nump}`exercice` (boucle while)

Sans l'exécuter, qu'affiche ce programme si:

1. `n = 0`?
2. `n = 9`?

Ensuite, exécutez le programme pour vérifier votre réponse.

```{exec} python
:editor:
n = ...
while n <= 5:
  print(n)
  n + 1
```

```{solution}
1. une infinité de 0
2. \
```

## Ordre d'exécution

### Exercice {nump}`exercice`

Sans exécuter le programme,

1. Indiquez l'ordre dans lequel les instructions seront exécutées (numéros de lignes).
2. Notez ce qui sera affiché sur la console.

Ensuite, exécutez le programme pour vérifier votre réponse.

```{exec} python
:editor:
nom = "Bob"
age = 16
print("Bonjour", nom, "vous avez", age + 1, "ans!")
```

```{solution}
1. 1 - 2 - 3
2. Bonjour Bob vous avez 17 ans!
```

### Exercice {nump}`exercice`

Sans exécuter le programme,
1. Indiquez l'ordre dans lequel les instructions seront exécutées.
(numéros de lignes).
2. Notez ce qui sera affiché sur la console.

Ensuite, exécutez le programme pour vérifier votre réponse.

3. Même question si on remplace la ligne 1 par `nombre = -8`
4. Même question si on remplace la ligne 1 par `nombre = 0`

```{exec} python
:editor:
nombre = 25
if nombre < 0:
  print("Ce nombre est nul.")
elif nombre == 0:
  print("Ce nombre est positif.")
else:
  print("Ce nombre est négatif.")
```

```{solution}
1. 1 - 2 - 4 -  6 - 7
2. Ce nombre est négatif.
3. 1 - 2 - 3 / Ce nombre est nul.
4. 1 - 2 - 4 - 5 / Ce nombre est positif.
```

### Exercice {nump}`exercice`

Sans exécuter le programme,
1. Indiquez l'ordre dans lequel les instructions seront exécutées.
(numéros de lignes).
2. Notez ce qui sera affiché sur la console.

Ensuite, exécutez le programme pour vérifier votre réponse.

```{exec} python
:editor:
n = 0
s = 3
for _ in range(2):
  n += 2
  s + 1
print("n =", n, "et s =", s)
```

```{solution}
1. 1 - 2 - 3 - 4 - 5 - 3 - 4 - 5 - 6
2. n = 4 et s = 3

```

### Exercice {nump}`exercice` (boucle while)

Sans exécuter le programme,
1. Indiquez l'ordre dans lequel les instructions seront exécutées.
(numéros de lignes).
2. Notez ce qui sera affiché sur la console.

Ensuite, exécutez le programme pour vérifier votre réponse.

```{exec} python
:editor:
n = 6
while n <= 10:
  print(n)
  n += 2
print("J'ai fini!")
```

```{solution}
1. 1 - 2 - 3 - 4 - 2 - 3 - 4 - 2 - 3 - 4 - 5
2. 6\
   8\
   10\
   J'ai fini!
```

### Exercice {nump}`exercice` (boucle while)

Nous aimerions programmer l'algorithme de Syracuse:

```{code-block} text
Choisir un nombre entier.
Si le nombre est pair, le diviser par 2.
S'il est impair, le multiplier par 3 et lui ajouter 1.
Afficher le nombre.
Répéter ces opérations jusqu'à obtenir 1.
```

Remarque: Cet algorithme se termine toujours par le suite 4, 2, 1.

Voici la liste des instructions, remettez-les dans l'ordre et indentez
correctement le code.


```{exec} python
:editor: b68bd0e3-e7c6-443e-a64d-f97a501eae1b
nombre = nombre / 2
while nombre != 1:
print(nombre)
else:
print("L'algorithme de Syracuse est terminé et il se termine bien par 4, 2 et 1!")
if nombre % 2 == 0:
nombre = int(input("Choisissez un nombre entier: "))
nombre = 3 * nombre + 1
```

````{solution}
```{exec} python
nombre = int(input("Choisissez un nombre entier: "))
while nombre != 1:
  if nombre % 2 == 0:
    nombre = nombre / 2
  else:
    nombre = 3 * nombre + 1
  print(nombre)
print("L'algorithme de Syracuse est terminé et il se termine bien par 4, 2 et 1!")
```
````

## Boucle `for` et boucle `while`

### Exercice {nump}`exercice` (boucle while)

Transformez le code suivant afin d'utiliser une boucle `while` à la place de la
boucle `for`.

```{exec} python
:editor: 5ccfcda3-f7f1-48c8-9c39-de4a7c9b254a
for i in range(20):
  print(i ** 2)
```

````{solution}
```{exec} python
n = 0
while n < 20:
  print(n ** 2)
  n += 1
```
````

### Exercice {nump}`exercice` (boucle while)

Transformez le code suivant afin d'utiliser une boucle `for` à la place de la
boucle `while`.

```{exec} python
:editor: 10459e39-ee44-45d1-9d8a-2278f911e8d3
n = 4
while n <= 10:
  print(2 * n)
  n += 1
```

````{solution}
```{exec} python
for i in range(4, 11):
  print(2 * i)
```
````

### Exercice {nump}`exercice` : Cryptarithme 1

Un cryptarithme est un casse-tête qui se présente comme une équation mathématique où les lettres représentent des chiffres à trouver. Il y a 3 règles de bases à respecter :
-	Deux lettres différentes remplacent toujours deux chiffres différents,
-	Deux chiffres différents sont toujours remplacés par deux lettres différentes
-	L'écriture d'un nombre ne commence jamais par zéro.

Le cryptarithme suivant :
```{flex-table}
{t=h}| |R|O|U|E
{t=h}| |R|O|U|E
{t=h}|=|=|=|=|=
{t=h}| |V|E|L|O
```
possède 3 solutions : 

-	2673 + 2673 = 5346  {hspace}`2em`	(R=2, O=6, U=7, E=3, V=5 et L=4)
-	2693 + 2693 = 5386  {hspace}`2em`	(R=2, O=6, U=9, E=3, V=5 et L=8)
-	4653 + 4653 = 9306  {hspace}`2em`	(R=4, O=6, U=5, E=3, V=9 et L=0)

Le programme ci-dessous permet de résoudre le cryptarithme ROUE + ROUE = VELO par force brute. Mais il ne respecte pas exactement les règles de base et retourne des solutions qui ne sont pas valides. Corrigez ce programme afin qu'il n'affiche que les solutions valides.
```{exec} python
:editor: 10459e39-ee44-45c1-9d8a-2278f921e8d4
# Résolution du Cryptarithme : ROUE + ROUE = VELO
# 3 solutions
nb_solution = 0
for R in range(10) :
    for O in range(10) :
        for U in range(10) :
            for E in range(10) :
                for V in range(1,10) :
                    for L in range(10) :
                        ok1 = R != O and R != U and R != E and R != V and R != L
                        ok2 = O != U and O != E and O != V and O != L
                        ok3 = U != E and U != V and U != L
                        ok4 = E != V and E != L
                        ok5 = V != L
                        if ok1 and ok2 and ok3 and ok4 and ok5 :
                            ROUE = R * 1000 + O * 100 + U * 10 + E
                            VELO = V * 1000 + E * 100 + L * 10 + O
                            if ROUE + ROUE == VELO :
                                print("ROUE + ROUE = VELO")
                                print(ROUE,"+",ROUE,"=",VELO, "\n")
                                nb_solution += 1

print("Il y a ", nb_solution, "solutions")
```

### Exercice {nump}`exercice` : Cryptarithme 2

Analysez le fonctionnement du programme de l'exercice précédent, puis adaptez-le ci-dessous afin de résoudre chacun des cryptarithmes suivants (en respectant toujours toutes les règles de base des cryptarithmes):
- NON + NON = OUI {hspace}`6em`( 2 solutions)
- UN+UN+NEUF=ONZE {hspace}`4.5em`	( 1 solution)
- UN + TROIS = DEUX + DEUX {hspace}`2em`	( 10 solutions)

```{exec} python
:editor: 3d40e18b-534c-48ae-a1a3-025ad03f9452
# Écrivez le programme ici
```






