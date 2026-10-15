% Copyright 2024 Caroline Blank <caro@c-space.org>
% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Fonctions

## Introduction

En programmation, une **fonction** est un bloc de code (suite d'instructions)
permettant de réaliser une tâche donnée et auquel nous donnons un nom.

Nous avons déjà rencontrées plusieurs fonctions dans les chapitres précédents:

- print(...): affiche sur la console ce qui est indiqué entre parenthèse
  ```{exec} python
  :when:
  print("Hello world")
  ```
- input(...): demande à l'utilisateur d'entrer une donnée
  ```{exec} python
  :when:
  prenom = input("Quel est ton prénom?")
  ```
- int(...): convertit ce qui est entre parenthèse en nombre entier
  ```{exec} python
  :when:
  age = int(input("Quel est ton âge?"))
  ```
- float(...): convertit ce qui est entre parenthèse en nombre à virgule
  ```{exec} python
  :when:
  prix = float(input("Quel est le prix de l'article?"))
  ```
- range(...): renvoie une liste de nombres (de 0 à la valeur entre parenthèse - 1)
  ```{exec} python
  :when:
  for _ in range(3):
    print("Bonjour!")
  ```

Toutes les fonctions ci-dessus sont des fonctions intégrées, elles ont été
prédéfinies pour nous. Nous pouvons les utilisez sans nous soucier de la manière
dont elles ont été implémentées.

## Modules

Un module est comme une boite à outils. Il contient plein de fonctions déjà
implémentées que nous pouvons utiliser. Par exemple, dans le module **math**, il
y a la fonction `sqrt(n)` qui permet de calculer la racine carré du nombre n,
ainsi que la constante &#960; notée `pi`. Dans le module **random**, la fonction
`randint(a, b)` permet de déterminer un nombre aléatoire entre a et b (inclus).

Avant de pouvoir utiliser une fonction d'un module, il faut l'importer ainsi:

```{exec} python
:when:
from nom_du_module import nom_de_la_fonction
```

On peut également directement importer toutes les fonctions d'un module en utilisant le joker:

```{exec} python
:when:
from nom_du_module import *
```
```{tip}
Toutes les importations se font au début du programme. De cette manière, on sait tout de suite quels sont les modules utilisés dans celui-ci.
```

### Exemple {num2}`exemple`

```{exec} python
:editor:
# import des modules
from math import sqrt, pi		# import de la fonction sqrt et de la constante pi du module math
from random import randint		# import de la fonction randint du module random

n = randint(1, 20)     # choisit un nombre aléatoire entre 1 et 20
print(n)
print(sqrt(40))        # calcule et affiche la racine carrée de 40
print(pi)              # affiche la valeur de la constante pi
```

### Exemple {num2}`exemple`

```{exec} python
:editor:
# import des modules avec le jocker
from math import *		# import de toutes les fonctions du module math
from random import *	# import de toutes les fonctions du module random

n = randint(1, 20)     # choisit un nombre aléatoire entre 1 et 20
print(n)
print(sqrt(40))        # calcule et affiche la racine carrée de 40
print(pi)              # affiche la valeur de la constante pi
```

## Définition et appel de fonctions

Comme vu dans l'introduction aux fonctions, il est possible de définir nos
propres fonctions au moyen du mot clé `def`, suivi du nom de la fonction et d'un bloc d'instructions.

Définir une nouvelle fonction permet notamment d'éviter les répétitions et de
découper un programme en plusieurs petites tâches plus faciles à résoudre. Ainsi
le code est plus lisible et plus facile à comprendre. Pour cela, il est
essentiel de choisir un nom de fonction qui explique ce qu'elle fait.

### Exemple {num2}`exemple`

```{exec} python
:editor:
# définition de la fonction
def calcule_et_affiche_aire_rectangle():
  cote_1 = 4
  cote_2 = 6
  aire = cote_1 * cote_2
  print(aire)

# appel de la fonction
calcule_et_affiche_aire_rectangle()
```

Cette fonction n'est pas très intéressante, car elle affiche toujours l'aire
d'un rectangle de côtés 4 et 6. Si je souhaite calculer l'aire d'un autre
rectangle, je dois définir une nouvelle fonction, ce qui n'est pas optimal.

Afin de modifier le comportement d'une fonction, nous pouvons utiliser des
paramètres (noms donnés aux éléments notés entre parenthèses dans la définition
de la fonction). Dans ce cours, l'appel de fonction se fera toujours avec le
même nombre d'arguments (valeurs des paramètres) et le même ordre que les
paramètres définis dans la fonction.

### Exemple {num2}`exemple`

```{exec} python
:editor:
# définition de la fonction
def calcule_et_affiche_aire_rectangle(cote_1, cote_2):
  aire = cote_1 * cote_2
  print(aire)

# appels de la fonction au moyen de valeurs numériques
calcule_et_affiche_aire_rectangle(10, 8)
calcule_et_affiche_aire_rectangle(2, 5.5)

largeur = 5
longueur = 12

# appel de la fonction au moyen des variables largeur et longueur
calcule_et_affiche_aire_rectangle(largeur, longueur)
```

De manière générale, la syntaxe de définition et d'appel de fonction est la
suivante:

```{exec} python
:when:
# définition de la fonction
def nom_de_la_fonction(parametre_1, parametre_2, ...):
  # instruction 1
  # instruction 2
  # ...

# appel de la fonction
nom_de_la_fonction(valeur_du_parametre_1, valeur_du_parametre_2, ...)
```

```{important}
Les instructions exécutées par la fonction appartiennent à un même **bloc d'instruction** et doivent avoir la même **indentation**.
```

```{important}
L'ordre des paramètres lors de l'appel de la fonction doit être le même que lors
de la définition de la fonction.
```

```{tip}
Une fonction doit toujours être définie avant d'être appelée, c'est pourquoi il
est préférable de placer toutes les définitions de fonctions au début du
programme juste après les imports.
```

## Exercices
### Exercice {num2}`exercice`

1. Définissez une fonction `calcule_et_affiche_perimetre_carre()`.
2. Combien de paramètres sont nécessaires?
3. Affichez le périmetre d'un carré de côté 7, d'un carré de côté 12, ainsi qu'en
   utilisant la variable `base`.

```{exec} python
:editor: 6871f44a-1dd8-4816-bb25-78b9e8e1e71b
# définition de la fonction
# complétez le code ici

base = 10

# appels de la fonction
# complétez le code ici
```


````{solution}
```{exec} python
# définition de la fonction
def calcule_et_affiche_perimetre_carre(cote):
  perimetre = 4 * cote
  print(perimetre)

base = float(input("Côté: "))

# appels de la fonction
calcule_et_affiche_perimetre_carre(7)
calcule_et_affiche_perimetre_carre(12)
calcule_et_affiche_perimetre_carre(base)
```
````

### Exercice {num2}`exercice`

Sans les exécuter, déterminez ce que vont afficher les programmes suivants.\
Font-ils ce qui est demandé?\
S'il y a une erreur, expliquez et corrigez le problème.

1.  Calculez l'aire d'un rectangle de côtés 20 et 100.

    ```{exec} python
    :editor:
    def calcule_et_affiche_aire_rectangle(largeur, longueur):
      aire = largeur * longueur
      print(aire)

    calcule_et_affiche_aire_rectangle(20, 100)
    ```

2.  Calculez l'aire d'un rectangle de côtés 40 et 15.

    ```{exec} python
    :editor:
    def calcule_et_affiche_aire_rectangle(largeur, longueur):
      aire = largeur * longueur
      print(aire)

    largeur = 40
    longueur = 15

    calcule_et_affiche_aire_rectangle(largeur, longueur)
    ```

3.  Calculez l'aire d'un rectangle de côtés 12 et 18.

    ```{exec} python
    :editor:
    def calcule_et_affiche_aire_rectangle(largeur, longueur):
      aire = largeur * longueur
      print(aire)

    base = 12
    hauteur = 18

    calcule_et_affiche_aire_rectangle(largeur, longueur)
    ```

4.  Calculez le prix d'un article qui coûte 35 CHF avec un rabais de 10%.

    ```{exec} python
    :editor:
    def calcule_et_affiche_pourcentage(prix, pourcentage):
      prix = (1 - pourcentage / 100) * prix
      print(prix)

    calcule_et_affiche_pourcentage(35, 10)
    ```

5.  Calculez le prix d'un article qui coûte 52 CHF avec un rabais de 15%.

    ```{exec} python
    :editor:
    def calcule_et_affiche_pourcentage(prix, pourcentage):
      prix = (1 - pourcentage / 100) * prix
      print(prix)

    calcule_et_affiche_pourcentage(15, 52)
	```

6.  Calculez l'aire d'un carré de côté 9.

    ```{exec} python
    :editor:
    def calcule_et_affiche_aire_carre(cote):
      aire = cote ** 2
      print(aire)

    cote = 9
    calcule_et_affiche_aire_carre()
    ```

7.  Calculez l'aire d'un disque de rayon 4.

    ```{exec} python
    :editor:
    def calcule_et_affiche_aire_disque(rayon):
      aire = rayon ** 2 * pi
      print(aire)

    calcule_et_affiche_aire_disque(4)
    ```

````{solution}
1.  Correct.
2.  Correct.
3.  Pas correct. Les variables `largeur` et `longueur` ne sont pas définies dans
    le programme. Il faut modifier la ligne 8 par:
    ```{exec} python
    :when:
    calcule_et_affiche_aire_rectangle(base, hauteur)
    ```
4.  Correct.
5.  Pas correct. Attention dans ce cas, l'ordre des paramètres a de
    l'importance. Il faut modifier la ligne 5 par:
    ```{exec} python
    :when:
    calcule_et_affiche_pourcentage(52, 15)
    ```
6.  Pas correct. La fonction `calcule_et_affiche_aire_carre(cote)` a un
    paramètre. Lorsqu'on l'appelle, il est obligatoire de passer un argument. Il
    faut modifier la ligne 6 par:
    ```{exec} python
    :when:
    calcule_et_affiche_aire_carre(cote)
    ```
7.  Pas correct. Il manque l'import de `pi` du module math. Il faut ajouter la
    ligne suivant au tout début de programme:
    ```{exec} python
    :when:
    from math import pi
    ```
````

### Exercice {num2}`exercice`

Complétez les programmes suivants uniquement où il y a des `...`:

1.  Calculez le périmètre d'un rectangle de côtés 4 et 7.

    ```{exec} python
    :editor:
    def calcule_et_affiche_perimetre_rectangle(..., ...):
      perimetre = 2 * (longueur + largeur)
      print(perimetre)

    ... = 4
    ... = 7
    calcule_et_affiche_perimetre_rectangle(cote_1, cote_2)
    ```

2.  Calculez le périmètre d'un carré de côté 11.

    ```{exec} python
    :editor:
    def calcule_et_affiche_perimetre_carre(cote):
      perimetre = 4 * ...
      print(perimetre)

    calcule_et_affiche_perimetre_carre(11)
    ```

3.  Calculez le périmètre d'un cercle de rayon 5.

    ```{exec} python
    :editor:
    from math import *

    def calcule_et_affiche_perimetre_cercle(...):
      perimetre = 2 * r * pi
      print(perimetre)

    rayon = 5
    calcule_et_affiche_perimetre_cercle(...)
    ```

### Exercice {num2}`exercice`

Sans l'exécuter, déterminez ce que va afficher le programme suivant. Ensuite,
exécutez-le pour vérifier votre réponse.

```{exec} python
def mystery_1(z):
  z += 1
  print(z)

def mystery_2(x):
  x *= 2
  if x >= 0:
    mystery_1(x + 2)
  else:
    mystery_1(x)

y = 5
mystery_1(y)
mystery_2(y)
mystery_2(y - 10)
print(y)
```

## Fonctions avec valeur de retour

La commande `return` sert à terminer l’exécution de la fonction et à transmettre un (ou plusieurs) résultat(s). Cette commande `return` n'est pas obligatoire à la fin de la fonction si il n'y a aucune valeur à retourner, mais il est recommandé de la mettre pour plus de clarté.

### Exemple {num2}`exemple:py-aire_du_cercle`

```{exec} python
:editor:
from math import pi
 
# calcul l'aire d'un cercle
def aire_cercle(rayon):
    aire=pi*rayon**2
    return aire

print("aire d'un cercle de rayon 1: ", aire_cercle(1))
print("aire d'un cercle de rayon 3: ", aire_cercle(3))
print("aire d'un cercle de rayon 10: ", aire_cercle(10))
```


### Exemple {num2}`exemple:py-delta2`

```{exec} python
:editor:
# définition des fonctions
def discriminant(a, b, c):
  return(b ** 2 - 4 * a * c)

# programme principal

# affiche le nombre de solution
delta = discriminant(1, 2, 1)
if delta > 0:
  print("L'équation a deux solutions.")
elif delta == 0:
  print("L'équation a une solution.")
else:
  print("L'équation n'a pas de solution.")
```
Améliorations possibles de l'exemple:

1.  Demandez les valeurs des coefficients `a`, `b` et `c` à l'utilisateur.
2.  Affichez les solutions quand elles existent.


```{role} aff(quiz-input)
:right: width: 8rem;
:check: lowercase trim
```
````{important}
`return` interrompt la fonction. Tout ce qui se trouve dans la fonction, mais
après le `return` sera ignoré.

```{exec} python
:linenos:
def double(x):
  return 2*x
  print("Ce texte ne s'affichera pas.")

print(double(5))
print("Fin du programme")
```
````

## Exercices
### Exercice {num2}`exercice`
Les cinq programmes ci-dessous sont similaires, mais les résultats sont à chaque fois différentse ressemblent. déterminez ce que va afficher chaque programme,
prédisez **ce qui s'affiche à l'écran**, puis vérifiez en réfléchissant à ce que fait vraiment
chaque appel de fonction. Si le programme n'affiche rien, écrivez `rien`.

```````{quiz}
1.  {aff}`5`
    ```{code-block} python
    def double(nombre):
        return nombre
	    nombre * 2

    print(double(5))
    ```

2.  {aff}`rien`
    ```{code-block} python
    def double(nombre):
        nombre = nombre * 2
	    return nombre

    double(5)
    ```

3.  {aff}`10`
    ```{code-block} python
    def double(nombre):
        return nombre * 2

    resultat = double(5)
    print(resultat)
    ```

4.  {aff}`30`
    ```{code-block} python
    def double(nombre):
        return nombre * 2

    print(double(5) + double(10))
    ```
```````

````{solution}
1.  **`5`**  La valeur retournée est le nombre reçu (5). La multiplication est effectuée seulement après la commande `return` et ne sera donc jamais exécutée.

2.  **`rien`** il n'a pas de print, la valeur retournée n'est ainsi pas utilisée 

3.  **`10`**. Cette fois l'appel est capté dans la variable `resultat`, que le `print` affiche ensuite.

4.  **`30`**. Un appel qui retourne une valeur peut s'utiliser directement dans un calcul :
    `double(5)` vaut 10, `double(10)` vaut 20, et c'est leur somme qui est affichée.

````

### Exercice {num2}`exercice`

Déterminez ce que font les programmes suivants et corrigez les erreurs.

1.  ```{exec} python
    :editor:
    def convertit_min_sec(min):
      return min * 60

    convertit_min_sec(145)
    print("145 minutes donnent", nb_secondes, "secondes.")
    ```

2.  ```{exec} python
    :editor:
    def convertit_sec_min(sec):
      min = sec / 60

    nb_minutes = convertit_sec_min(38700)
    print("38700 secondes donnent", nb_minutes, "minutes.")
    ```

3.  ```{exec} python
    :editor:
    def calcule_double_moins_trois(x):
      x = 2 * x
      return x
      x = x - 3

    print(calcule_double_moins_trois(4))
    ```

````{solution}

 1. Il faut sauvegarder la valeur de retour dans la variable nb_secondes
    ```{exec} python
    :linenos:
    def convertit_min_sec(min):
      return min * 60

    nb_secondes = convertit_min_sec(145)
    print("145 minutes donnent", nb_secondes, "secondes.")
    ```

2.  Il manque le `return` dans la fonction. Dans ce cas, la valeur retournée est
    `None`.
    ```{exec} python
    :linenos:
    def convertit_sec_min(sec):
      return sec / 60

    nb_minutes = convertit_sec_min(38700)
    print("38700 secondes donnent", nb_minutes, "minutes.")
    ```

3.  Le `return` n'est pas à la bonne place.
    ```{exec} python
    :linenos:
    def calcule_double_moins_trois(x):
      x = 2 * x
      x = x - 3
      return x

    print(calcule_double_moins_trois(4))
    ```
````

### Exercice {num2}`exercice`

Sans l'exécuter, déterminez ce que va afficher le programme suivant. Ensuite,
exécutez-le pour vérifier votre réponse.

```{exec} python
:editor:
def mystery_1(z):
  z *= 2
  return z

def mystery_2(x):
  x -= 7
  if x < 0:
    return x
  else:
    return x % 2

y = 5
print(mystery_1(y))
print(mystery_2(y))
print(mystery_2(2 * y))
print(y // 2)
```

### Exercice {num2}`exercice`

Complétez le programme ci-dessous. Nous avons défini une fonction `majeur` pour
tester si une personne est majeure ou pas.

```{exec} python
:editor: d62933bb-5602-48e8-b92e-302c5857b135
def majeur(age):
  if ... :
    return True
  else:
    return False

# Demandez son âge à l'utilisateur
age = ...

if majeur(age):
  print("Tu as le droit de vote")
else:
  print("Tu pourras voter dans", ..., "ans.")
```

````{solution}
```{exec} python
def majeur(age):
  if age >= 18 :
    return True
  else:
    return False

# Demandez son âge à l'utilisateur
age = int(input("Quel âge as-tu?"))

if majeur(age):
  print("Tu as le droit de vote")
else:
  print("Tu pourras voter dans", 18 - age, "ans.")
```
````

### Exercice {num2}`exercice`

1. Écrivez une fonction qui convertit un nombre de bits en octets.
2. Écrivez une fonction qui convertit un nombre d'octets en bits.
3. Convertissez 3664000 bits en octets.
4. Convertissez 512 octets en bits.

```{tip}
Un octet contient 8 bits.
```

```{exec} python
:editor: 6d5cee90-7949-4078-b22d-e2c84a39f4d4
# Écrire le programme ici
```

````{solution}
```{exec} python
:linenos:
# Convertit des bits en octets
def conversion_bits_octets(a):
  return a / 8

# Convertit des bits en octets
def conversion_octets_bits(a):
  return a * 8

nb_octets = conversion_bits_octets(3664000)
print("La conversion de 3664000 bits en octets donne", nb_octets)

nb_bits = conversion_octets_bits(512)
print("La conversion de 512 octets en bits donne", nb_bits)

```
````

### Exercice {num2}`exercice`

Reprenez les claculs de conversion Celsius et Fahrenheit que l'on a fait dans le chapitre *Entrées et sorties* afin de définir une fonction `Conversion_Celsius_Fahrenheit()` et une fonction `Conversion_Fahrenheit_Celsius()`.
Faites un petit programme de test qui répète 10 fois l'opération suivante:

1. Génère une température aléatoire *c* en Celsius: utilisez la fonction `randint()` vue en haut de la page
2. Convertit cette température en Fahrenheit 
3. Convertit cette température à nouveau en Celsius 
4. Affiche un message d'erreur si le résultat de la double conversion n'est pas égal à la température aléatoire *c* originale

```{exec} python
:editor: 5f6ee3a3-ab47-43c5-9774-f50cabd75e94
from random import randint		# import de la fonction randint du module random
# Complétez le programme


```

````{solution}
```{exec} python
:linenos:
from random import randint	# import de la fonction randint du module random

# conversion °C->°F
def Conversion_Celsius_Fahrenheit(c):
   return c*9/5 +32

# conversion °F->°C
def Conversion_Fahrenheit_Celsius(f):
   return (f - 32) / 1.8
   
# test: si on convertit °C->°F->°C on doit retomber sur la valeur initiale
nb_tests = 10
nb_succes = 0
for i in range(nb_tests):
   c = randint(-40, 50)
   f = Conversion_Fahrenheit_Celsius(c)
   c2 = Conversion_Celsius_Fahrenheit(f)
   print(c, f, c2)
   if abs(c-c2)< 0.001:
     nb_succes += 1
print()
if nb_tests == nb_succes :
    print("Le test est réussi!")
else:
    print("Le test est raté!")

```
````

### Exercice {num2}`exercice`
On veut déterminer si un nombre est premier. Pour ceci, nous allons créer 3 fonctions:
1.  Ecrivez une fonction `est_diviseur()` qui permet de déterminer si un nombre est diviseur d'un autre nombre
	```{exec} python
    :editor: 70746cc6-1686-423d-8665-560905cfc917

	def est_diviseur(nombre, diviseur):
	# à compléter
	

	# test de la fonction
    n = int(input("nombre: "))
    d = int(input("diviseur: "))
    print(n , "et", d, ": ", est_diviseur(n, d)) 
    ```

2.  Une fois que vous avez bien testé votre fonction `est_diviseur()` avec plusieurs paires de nombres, utilisez-la pour définir une nouvelle fonction `plus_petit_diviseur()` qui reçoit un nombre et retourne son plus petit diviseur (qui est plus grand ou égal à 2).
    ```{exec} python
    :editor: bba5d2de-9a45-4200-bdd2-570905cfc920
    def plus_petit_diviseur(...)
	# à compléter
	
    # test de la fonction
	
    ```

3.  Une fois que vous avez bien testé votre fonction `plus_petit_diviseur()` avec plusieurs nombres, utilisez-la pour définir une nouvelle fonction `est_premier()` qui reçoit un nombre et retourne `True` si son plus petit diviseur est égal à lui-même.
    ```{exec} python
    :editor: dc86de5e-ba35-4f9d-ba0e-570905cfc921
    # Écrivez votre programme ici
    ```
4. Complétez votre programme en demandant à l'utilisteur un nombre, en vérifiant que le nombre entré est bien un nombre positif et en affichant si ce nombre est premier ou pas.
5. Testez votre fonction avec différents [nombre premiers](https://www.nombres-premiers.fr/liste.html) et non-premiers.


````{solution}
```{exec} python
:linenos:
def est_diviseur(nombre, diviseur):
  if nombre % diviseur == 0:
    return True
  else:
    return False

def plus_petit_diviseur(nombre):
  for i in range(2, nombre+1):
    if est_diviseur(nombre, i):
      return i 

def est_premier(nombre):
  if plus_petit_diviseur(nombre) == nombre:
    return True
  else:
    return False

nombre = int(input("Choisir un nombre entier strictement positif:"))
while nombre <= 0:
  nombre = int(input("Le nombre doit être strictement positif!"
        "Choisir un nombre entier strictement positif:"))

if est_premier(nombre):
  print(nombre, "est un nombre premier.")
else:
  print(nombre, "n'est pas un nombre premier.")

```
````
