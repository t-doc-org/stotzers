% Copyright 2024 Caroline Blank <caro@c-space.org>
% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Introduction

## Qu'est-ce qu'un langage de programmation?

Un langage de programmation est une notation qui permet de communiquer avec
l'ordinateur.

Comme le français ou l'allemand, ce langage comprend:

- un alphabet (chiffres, lettres, ...)
- un vocabulaire (instructions, des mots réservés, ...)
- une syntaxe (ponctuation, indentation, ...)

Exemple:

```{exec} python
:when:
:linenos:
prenom = input("Quel est ton prénom? ")
age = int(input("Quel est ton âge? "))
print("Salut", prenom, "!")
if age >= 18:
  print("Tu es majeur(e).")
else:
  print("Tu es mineur(e).")
```

## Type de langages

Il existe des langages de **bas niveau** et des langages de **haut niveau**.

Les langages de bas niveau, comme l'assembleur, sont très proches du code
machine.

```{code-block}
:linenos:
.model small
.stack 100h

.data
msg db 'Hello world!$'

.code
start:
  mov ah, 09h     ; display the message
  lea dx, msg
  int 21h
  mov ax, 4C00h   ; terminate the executable
  int 21h
end start
```

Les langages de haut niveau, comme le python, sont très proches de l'anglais.

```{exec} python
:linenos:
print("Hello world!")
```

Il existe des centaines de langages de programmation qui ont des caractéristiques différentes, il faut choisir son langage en fonction de ses
besoins:

- Haut ou bas niveau
- Facilité d'utilisation
- Sureté
- Rapidité
- Puissance
- ...

## Python

Le langage **Python** a été créé par [Guido Van Rossen](https://fr.wikipedia.org/wiki/Guido_van_Rossum)
en 1989. Il a écrit une première version pendant ses vacances de Noël. La première version publique a été publiée en février 1991.

Il a décidé de baptiser ce projet Python, car il est fan de la série télévisée
***Monty Python's Flying Circus***.

## Le langage Python
Voici les 33 mots-clés du langage Python : 

```{flex-table}
:class: grid align-center
{t=b}|`and`  	    | `as`   |`assert`| `break` 	|`class`| `continue` | `def`   
{t=b}| `del`| `elif` | `else` | `except` |`False` |`finally` | `for`  
{t=b}| `from`| `global`|`if`   | `import` | `in`     | `is`     | `lambda` 
{t=b}|`None`  | `nonlocal` |`not`  | `or` | `pass`|`raise`| `return` 
{t=b}| `True` |`try` | `while`  | `with` | `yield` | | 
```

```{Attention}
- Python est sensible à la casse, ce qui signifie qu'il fait la différences entre minuscules et majuscules.
- Les mots-clés booléens `True` et `False` prennent obligatoirement une majuscule initiale.
- La commande print() n'est pas un mot clé mais une fonction built-in (on expliquera la différence plus tard)
```

## Pourquoi programmer à l'école ?
- Raisonner: Développer la logique et la pensée critique, analyser un problème, le découper en étapes logiques et le résoudre
- Être créatif : Écrire du code c’est créer
- Comprendre: Apprendre à programmer aide à comprendre comment les outils numériques actuels.
- Persévérance : Le code marche rarement du premier coup. Il ne faut pas abandonner face aux difficultés!

## Pourquoi apprendre Python à l'école ?

- Syntaxe simple et facile à comprendre
- Langage polyvalent et très utilisé (notamment dans les milieux académiques et scientifiques)
- Il y a de nombreuses librairies disponibles
- Libre et gratuit
- Langage adapté à beaucoup de domaines:
    - développement
    - interface Web
    - analyse de données
    - intelligence artificielle
	- robotique
    - scripting
    - jeux
    - ...

