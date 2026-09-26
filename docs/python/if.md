% Copyright 2024 Caroline Blank <caro@c-space.org>
% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Instructions conditionnelles

Une instruction conditionnelle est composée d'une **condition** puis d'un
**bloc d'instructions**. La condition est une expression ou une variable logique
évaluée par `True` ou `False`. Le bloc d'instructions s'exécute seulement si la
condition est vérifiée.

```{important}
Un **bloc d'instructions** est un groupe d'instructions qui doivent être exécutées ensemble.
En Python, les instructions d'un même bloc sont reconnaissables car elles ont toutes exactement la même **indentation**.

L'**indentation** consiste à décaler une instruction vers la droite, généralement avec 4 espaces (ou une tabulation).
```

## Exemple {num2}`exemple` (if)

Le bloc d'instructions ne sera exécuté que si la condition est vraie.

```{figure} images/if.png
:alt: Ordinogramme if
:width: 300px
:align: center
```

```{exec} python
:editor:
print("Début")
meteo = "soleil"
print("Je mets ma veste.")
if meteo == "pluie":
    print("Je prends un parapluie.")
print("Je pars.")
print("Fin")
```

Dans l'exemple ci-dessus, il ne se passe rien, la condition n'est pas vérifiée.\
Changez la valeur de la variable `meteo` en "pluie". Que se passe-t-il?

## Exemple {num2}`exemple` (if ... else)

Le bloc d'instructions après le `if` sera exécuté si la condition est vraie,
sinon ce sera le bloc d'instructions du `else` qui sera exécuté.

```{figure} images/if-else.png
:alt: Ordinogramme if-else
:width: 500px
:align: center
```

```{exec} python
:editor:
moyenne = 5
print("La moyenne est de", moyenne)

if moyenne >= 4:
    print("Moyenne suffisante")
else:
    print("Moyenne insuffisante")

print("Pour réussir, il faut travailler!")
```

Dans l'exemple ci-dessus, soit la moyenne est suffisante (moyenne supérieure ou
égale à 4), soit elle est insuffisante (moyenne inférieure à 4). Il n'y a pas
d'autres possibilités. Changez la valeur de la variable `moyenne` en 3. Que se
passe-t-il?

## Exemple {num2}`exemple` (if ... elif ... else)

Certaines situations nécessitent de distinguer plus qu'un ou deux cas.

```{figure} images/if-elif-else.png
:alt: Ordinogramme if-elif-else
:width: 100%
:align: center
```

```{exec} python
:editor:
type_film = "comédie"
print("Le type de film est", type_film)

if type_film == "action":
    print("Explosions et des cascades de folie!")
elif type_film == "comédie":
    print("Mort de rire!")
elif type_film == "horreur":
    print("Terrifiant!")
else:
    print("Je ne connais pas.")

print("Bonne séance de cinéma!")
```

Dans l'exemple ci-dessus, il y a le choix entre trois types de films (action,
comédie et horreur). Le branchement `else` gérera tous les autres cas. Remplacer
la valeur de la variable `type_film` par "action", "horreur" ou "drame". Que se
passe-t-il?

### Exercice {num2}`exercice`

Écrivez l'algorithme suivant en Python:

```{code-block} text
Demander à l'utilisateur d'entrer un nombre positif et sauvegarder la valeur dans la variable a
Si a est plus petit que 0 alors
  écrire "Ce nombre n'est pas positif."
```

```{exec} python
:editor: f0cd9039-aa2a-4a6e-a855-ad51d4cd557e
a = float(input("Entrez un nombre positif: "))
# Complétez le programme ici
```

````{solution}
```{exec} python
:linenos:
a = float(input("Entrez un nombre positif: "))
if a < 0:
  print("Ce nombre n'est pas positif.")
```
````

### Exercice {num2}`exercice`

Écrivez l'algorithme suivant en Python:

```{code-block} text
Demander à l'utilisateur d'entrer la valeur de a et sauvegarder la valeur dans la variable a
Demander à l'utilisateur d'entrer la valeur de b et sauvegarder la valeur dans la variable b
Si a est plus petit que b alors
  écrire "a est plus petit que b"
Sinon
  écrire "a est plus grand que b"
```

```{exec} python
:editor: 3d40e18b-534c-48ae-a1a3-025ad03f9392
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
a = float(input("Valeur de a: "))
b = float(input("Valeur de b: "))
if a < b:
  print("a est plus petit que b.")
else:
  print("a est plus grand que b.")
```
````

### Exercice {num2}`exercice`

Reprenons l'exercice précédent. Que se passe-t-il si a est égal à b?

Améliorez le programme précédent en traitant aussi le cas où a est égal à b.

```{exec} python
:editor: d5a6da62-0c1a-4ea7-a1b2-910848086c35
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
a = float(input("Valeur de a: "))
b = float(input("Valeur de b: "))
if a == b:
  print("a est égal à b.")
elif a < b:
  print("a est plus petit que b.")
else:
  print("a est plus grand que b.")
```
````

### Exercice {num2}`exercice`

```{exec} python
:editor: 49f2047d-751c-42d6-8832-40953fa8db92
# Complétez le programme seulement où il y a les ...
a = ...       # choisissez une valeur pour a
if ... :
  print("a est plus grand que 5.")
elif ... :
  print("a est égal à 5.")
else:
  print("a est ...")
```

Tester la justesse de votre code avec différentes valeurs de a.

````{solution}
```{exec} python
:editor:
a = ...                                 # choisir la valeur de a
if a > 5:
  print("a est plus grand que 5.")
elif a == 5:                           # a == 5 pour la comparaison
  print("a est égal à 5.")
else:
  print("a est plus petit que 5.")
```
````

### Exercice {num2}`exercice`

```{role} input(quiz-input)
:right: width: 10rem;
:check: json remove lowercase
```

````{quiz}
{input}`{"0": true, "-x+2": "Il faut remplacer x par sa valeur."}`
Que va afficher ce programme?

```{code-block} python
:linenos:
x = 2
if x <= -1:
  print(2 * x + 1)
elif x <= 3:
  print(-x + 2)
else:
  print(2 * x - 5)
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui demande son âge à l'utilisateur et affiche s'il est
majeur ou s'il est mineur.

```{exec} python
:editor: c590c718-c33d-43da-a078-f7eb37502f9c
age = int(input("Quel est ton âge?"))

# Complétez le programme ici
```

````{solution}
```{exec} python
age = int(input("Quel est ton âge? "))

if age < 18:
  print("Tu es mineur.")
else:
  print("Tu es majeur.")
```
````

### Exercice {num2}`exercice`

Indiquez l'ordre d'exécution (N° de ligne) et ce qui va être affiché par chacun des programmes suivants.

1.  ```{exec} python
    :when:
    :linenos:
    a = 2
    if a != 2:
        print("Rouge")
    elif a < 2:
        print("Bleu")
    else:
        print("Jaune")
    ```

    ````{solution}
    1 - 2 - 4 - 6 - 7

    ```{exec} python
    :linenos:
    a = 2
    if a != 2:
        print("Rouge")
    elif a < 2:
        print("Bleu")
    else:
        print("Jaune")
    ```
    ````

2.  ```{exec} python
    :when:
    :linenos:
    y = 2
    if y <= -1:
        y = 3 * y + 5
    elif y <= 3:
        y += 4
    else:
        y = y * y - 1
    print(y)
    ```

    ````{solution}
    1 - 2 - 4 - 5 - 8

    ```{exec} python
    :linenos:
    y = 2
    if y <= -1:
        y = 3 * y + 5
    elif y <= 3:
        y += 4
    else:
        y = y * y - 1
    print(y)
    ```
    ````

### Exercice {num2}`exercice`

Le programme suivant est censé affiché le tarif appliqué en fonction de l'âge de
l'utilisateur. Mais il contient une erreur par ligne, trouvez-les et corrigez-les.

```{exec} python
:editor: 55bcea11-979f-43f8-8d1c-46f102e56b2b
age = input("Quel âge as-tu? ")
if age > 18:
print("Tu payes le tarif enfant.")
elif age < 65
  print "Tu payes le tarif adulte."
else age >= 65:
  print(Tu payes le tarif retraité.)
```

````{solution}
```{exec} python
age = int(input("Quel âge as-tu? "))
if age < 18:
    print("Tu payes le tarif enfant.")
elif age < 65:
    print("Tu payes le tarif adulte.")
else:
    print("Tu payes le tarif retraité.")
```
````

### Exercice {num2}`exercice`

Écrivez un algorithme qui:
- demande un nombre à l'utilisateur,
- soustrait 5,5 à ce nombre,
- si le résultat est négatif, lui ajoute 10,
- affiche le résultat obtenu.

```{exec} python
:editor: d17fb574-66ce-4774-83fa-279a38ff862d
# Écrivez le programme
```

````{solution}
```{exec} python
nombre = float(input("Choisissez un nombre"))
nombre = nombre - 5.5
if nombre < 0:
    nombre += 10
print(nombre)
```
````

### Exercice {num2}`exercice`

Voici trois programmes:

1. Quelles sont les différences?
2. Indiquez l'ordre d'exécution des lignes.
3. Que vont-ils afficher?

````{list-grid}
:style: grid-template-columns: 1fr 1fr 1fr;
- # Programme 1
  ```{exec} python
  :linenos:
  x = -1
  if x < 0:
    x = x + 5
  elif x < 5:
    x = x * 3
  elif x < 10:
    x = x - 6
  else:
    x = 1000
  print(x)
  ```
- # Programme 2
  ```{exec} python
  :linenos:
  x = -1
  if x < 0:
    x = x + 5
  if x < 5:
    x = x * 3
  if x < 10:
    x = x - 6
  else:
    x = 1000
  print(x)
  ```
- # Programme 3
  ```{exec} python
  :linenos:
  x = -1
  if x < 0:
    x = x + 5
    if x < 5:
      x = x * 3
      if x < 10:
        x = x - 6
  else:
    x = 1000
  print(x)
  ```
````

### Exercice {num2}`exercice`

Le programme suivant contient une erreur de logique. Testez le programme avec
différentes valeurs pour trouver et corriger l'erreur.

```{exec} python
:editor: 8f95d8ea-d2c0-4d56-a399-a58c54e99e6c
age = 18
if age >= 18:
  print("Tu payes le prix adulte.")
elif age >= 65:
  print("Tu payes le prix retraité")
else:
  print("Tu payes le prix enfant.")
```

```{solution}
Le `elif` ne sera jamais exécuté, car si l'âge est supérieur ou égal à 65, il
est aussi supérieur ou égal à 18. Donc la condition du `if` sera vérifiée.

Il faut donc tester les conditions par ordre croissant: enfant, adulte, retraité
ou par ordre décroissant: retraité, adulte, enfant.
```

### Exercice {num2}`exercice`

Un zoo pratique les tarifs suivants:

- Les enfants jusqu'à 16 ans révolus payent 15 francs.
- Les jeunes entre 16 et 20 ans payent 22 francs.
- Les adultes à partir de 21 ans payent 28 francs.

Écrivez un programme qui demande l'âge de l'utilisateur et affiche le prix à
payer.

Le rendu du programme doit être le suivant:
```{code-block} text
Quel est ton âge? 16
Pour une personne de 16 ans, le prix à payer est de 22 francs.
```

```{exec} python
:editor: a7451ba3-2bd7-46f5-a2c6-1ab83c16c970
# Écrivez le programme
```

````{solution}
```{exec} python
age = int(input("Quel est ton âge?"))
if age < 16:
  prix = 15
elif age <= 20:
  prix = 22
else :
  prix = 28
print ("Pour une personne de", age, "ans, le prix à payer est de", prix, "francs.")
```
````

### Exercice {num2}`exercice`
Ecrivez un programme qui demande à l’utilisateur le nombre de bouteilles qu’il achète et lui indique en retour le rabais auquel il a droit, comme indiqué à la figure ci-dessous.

```{image} images/rabais_progressif.png
:alt: Rabais progressif
:width: 80%
:align: center
```

```{exec} python
:editor:  a7451ba3-2bd7-46f5-a2c6-1ab83c16c960
# Écrivez le programme
```
Pour valider votre programme, il est important de tester tous les cas de figure et les cas particuliers.

````{solution}
```{exec} python
# calcule le rabais en fonctions du nombre de bouteilles achetées
nombreDeBouteilles = int(input("Combien de bouteilles achetez-vous? "))
rabais = 0
if nombreDeBouteilles > 120:
   rabais = 25
elif nombreDeBouteilles > 60:
    rabais = 20
elif nombreDeBouteilles > 30:
    rabais = 15
elif nombreDeBouteilles > 12:
    rabais = 10
else:
    rabais = 0
print("Avec ", nombreDeBouteilles, " bouteilles, vous avez droit à un rabais de ", rabais, " %")
```
````

### Exercice {num2}`exercice`

Julien souhaite s'inscrire à des séances d'équitation. Le club propose deux type
de tarification:

- Tarif A: Avec un abonnement annuel de 185 francs, la séance coûte 11 francs.
- Tarif B: Sans abonnement, la séance coûte 17 francs.

Écrivez un programme qui demande à Julien le nombre de séance qu'il voudrait
suivre pendant l'année et afficher le tarif le plus avantageux dans ce cas.

```{exec} python
:editor: f5b7f840-9b9e-4f66-9502-36f2f995abcb
nb_seances = int(input("Nombre de séances: "))

# Complétez le programme
prixA = ...
prixB = ...
```

````{solution}
```{exec} python
nb_seances = int(input("Nombre de séances: "))

prix_A = 11 * nb_seances + 185
prix_B = 17 * nb_seances
if prix_A < prix_B:
  print("Le tarif A est le plus avantageux.")
elif prix_B < prix_A:
  print("Le tarif B est le plus avantageux.")
else:
  print("Les deux tarifs sont équivalents.")
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui demande trois nombres à l'utilisateur et affiche le
maximum (le plus grand).

```{exec} python
:editor: c3d6fb9b-eb5f-4e83-b662-606ac68282cf
nombre_1 = float(input("Choisir un premier nombre: "))
nombre_2 = float(input("Choisir un deuxième nombre: "))
nombre_3 = float(input("Choisir un troisième nombre: "))

# Complétez le programme ici
```

````{solution}
```{exec} python
nombre_1 = float(input("Choisir un premier nombre: "))
nombre_2 = float(input("Choisir un deuxième nombre: "))
nombre_3 = float(input("Choisir un troisième nombre: "))
if nombre_1 > nombre_2 and nombre_1 > nombre_3:
  print("Le plus grand nombre est", nombre_1)
elif nombre_2 > nombre_1 and nombre_2 > nombre_3:
  print("Le plus grand nombre est", nombre_2)
else:
  print("Le plus grand nombre est", nombre_3)
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui demande un nombre entier à l'utilisateur et affiche
s'il est pair ou impair.

````{tip}
:class: dropdown
Utilisez le modulo (reste de la division entière) pour déterminer si un nombre
est divisible par un autre nombre.

```{exec} python
:editor:
print(14 % 5)          # Tester avec d'autres valeurs
```
````

```{exec} python
:editor: 085b1907-ca58-4a00-aab4-bcde5e4092cd
# Écrivez le programme ici
```

````{solution}
```{exec} python
nombre = int(input("Choisir un nombre entier: "))
if nombre % 2 == 0:
  print(nombre, "est pair.")
else:
  print(nombre, "est impair.")
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui demande un nombre entier à l'utilisateur et affiche
s'il est divisible par 3 et 13.

```{exec} python
:editor: 1f78a8da-5f0e-452d-b427-59943fea89f2
# Écrivez le programme ici
```

````{solution}
```{exec} python
nombre = int(input("Choisir un nombre entier: "))
if nombre % 3 == 0 and nombre % 13 == 0:
  print(nombre, "est divisible par 3 et 13.")
elif nombre % 3 == 0:
  print(nombre, "est divisible par 3.")
elif nombre % 13 == 0:
  print(nombre, "est divisible par 13.")
else:
  print(nombre, "n'est divisible ni par 3, ni par 13.")
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui permet de résoudre des équations du deuxième degré de la forme $ax^2+bx+c=0$. Ce
programme doit tout d'abord demander à l'utilisateur les valeurs $a$, $b$ et $c$, puis indiquer le nombre de solutions, les calculer et les afficher.

```{exec} python
:editor: 71c23a46-21ab-4874-a8be-1928ea37c625
# Écrivez le programme ici
```

````{solution}
```{exec} python
from math import sqrt

# Demande à l'utilisateur les valeurs des coefficients a, b et c
print("Résolution d'équation du 2e degré")
a = float(input("Entrer le coefficient de x^2: "))
b = float(input("Entrer le coefficient de x: "))
c = float(input("Entrer la partie littérale: "))

print("Je vais résoudre l'équation ", a, "x^2+", b, "x+",c, "=0 ")
if a == 0:
  print("Ce n'est pas une équation du deuxième degré.")
  print("La solution de l'équation est", -c / b)
else:
  delta = b ** 2 - 4 * a *c

  if delta < 0:
    print("Cette équation n'a pas solution.")
  elif delta == 0:
    x = -b / (2 * a)
    print("Cette équation a une seule solution: x =", x)
  else:
    x_1 = (-b + sqrt(delta)) / (2 * a)
    x_2 = (-b - sqrt(delta)) / (2 * a)
    print("Cette équation a deux solutions: x_1 =", x_1, "et x_2 =", x_2)
```
````
