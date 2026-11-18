% Copyright 2024 Caroline Blank <caro@c-space.org>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Erreurs

En appuyant sur le bouton {kbd}`Run`, Python va d'abord **compiler** le
programme et ensuite l'**exécuter**.

## Compilation

Lors de la compilation, Python
1. lit le code,
2. vérifie qu'il ne comprend pas d'erreur de syntaxe,
3. transforme le code en un langage compréhensible par l'ordinateur.

## Exécution

L'exécution sera effectuée seulement s'il n'y a pas eu de problème pendant
la compilation. Python va exécuter les instructions du programme, suivant un
ordre bien défini.

En programmation, il existe trois types d'erreurs:
1. Les erreurs de syntaxe
2. Les erreurs d'exécution
3. Les erreurs de logique

## Erreur de syntaxe

Les erreurs de syntaxe sont détectées lors de la compilation. Python vérifie que
la syntaxe est correcte:
- les `:` sont présents et au bon endroit &rarr; Sinon `SyntaxError`
- une parenthèse ouverte est toujours fermée &rarr; Sinon `SyntaxError`
- un guillemet ouvert est toujours fermé &rarr; Sinon `SyntaxError`
- l'indentation est correcte &rarr; Sinon `IndentationError`
- ...

Si Python trouve une erreur de syntaxe, le programme s'arrête, car il ne
comprend pas le programme et ne peut donc pas l'exécuter. L'erreur est affichée
sur la console.

### Exemple {num2}`exemple`

```{exec} python
:editor:
n = 7
if n < 10
  print("n est plus petit que 10.)
else:
  print("n est plus grand ou égal à 10."
```

## Erreur d'exécution

Les erreurs d'exécution sont détectée pendant l'exécution. La syntaxe est
correcte, mais une instruction lui demande de faire quelque chose d'"illégal",
par exemple:
- une division par zero &rarr; `ZeroDivisionError`
- accéder à la valeur d'une variable qui n'existe pas &rarr; `NameError`
- appeler une fonction avec un nombre de paramètres incorrect &rarr; `TypeError`

Si Python trouve une erreur d'exécution, il "plante", c'est-à-dire qu'il
s'arrête de manière abrupte.

### Exemple {num2}`exemple`

```{exec} python
:editor:
a = 7
b = 0
print(a / b)
print(c)
```

## Erreur de logique

Python ne détecte aucune erreur, le programme est compilé et exécuté, mais le
résultat n'est pas celui attendu.

### Exemple {num2}`exemple`

```{exec} python
:editor:
# Ce programme va afficher les nombres pairs plus petits que 20.
n=0
while n > 20:
  print(n)
  n = n + 2
```

```{important}
Les erreurs de syntaxe sont détectées par le compilateur qui affiche un message d'erreur.

Par contre, les erreurs d'exécution et de logique ne produisent pas systématiquement de message d'erreur. Lorsqu'on écrit un programme, il est donc important de **tester tous les différents cas possibles**, afin de trouver toutes les erreurs d'exécution et de logique. 

Pour l'exercice 2 ci-dessous, par exemple, il faut par exemple tester le programme au moins 3 fois: une fois avec un âge qui correspond au tarif enfant, une fois pour le tarif adulte et une fois pour le tarif retraité)
```

## Exercices

### Exercice {num2}`exercice`

Les programmes suivants contiennent tous une erreur.
- Trouvez l'erreur, si possible sans exécuter le programme.
- Déterminez son type (syntaxe, exécution, logique).
- Corrigez-la.

1.  ```{exec} python
    :editor:
    :reset: show
    longueur = float(input("Entrez la longueur du rectangle:"))
    aire = longueur * largeur
    print(aire)
    ```

2.  ```{exec} python
    :editor:
    :reset: show
    n = 0
    while n < 10:
    print(n)
    n += 2
    ```

3.  ```{exec} python
    :editor:
    :reset: show
    a = 12
    b = a / 4
    b -= 3
    print(a)
    print(b)
    print(a/b)
    ```

4.  ```{exec} python
    :editor:
    :reset: show
    i = 0
    while i < 4
      print(i)
      n += 1
    ```

```{solution}
1. Erreur d'exécution: la variable larg n'est pas définie.
2. Erreur de syntaxe: l'indentation n'est pas correcte.
3. Erreur d'exécution: il n'est pas possible de diviser par 0.
4. Erreur de syntaxe: il manque les :.
```

### Exercice {num2}`exercice`

Le programme suivant contient une erreur de logique. Testez le programme avec
différentes valeurs pour la trouver et corrigez-la.

```{exec} python
:editor:
:reset: show
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
```
