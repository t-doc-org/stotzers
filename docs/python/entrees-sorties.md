% Copyright 2024 Caroline Blank <caro@c-space.org>
% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Entrées et sorties

## Fonction `print()`

La fonction `print()` permet d'afficher une phrase ou la valeur d'un objet sur
la console.

### Exemple {num2}`exemple`

1.  Affichage d'une chaine de caractère. Ce qui se trouve entre guillemets sera
    affiché tel quel.

    ```{exec} python
    :editor:
    print("Hello world!")
    ```

2.  Affichage de la valeur d'une variable.

    ```{exec} python
    :editor:
    a = 10
    print(a)
    a += 5
    print(a)
    ```

3.  Affichage d'une chaîne de caractère et de la valeur d'une variable. Il faut
    utiliser une virgule pour séparer les différents éléments.

    ```{exec} python
    :editor:
    prix_choco = 17.20
    print("Le prix de la boîte de chocolat est de", prix_choco, "CHF.")
    ```

### Exercice {num2}`exercice`

Écrivez un programme qui affiche exactement ce texte:

```{exec} python
:then: py-ex-1-sol
:when: load
:class: hidden
```

```{exec} python
:editor: 39661323-0c23-419d-9d91-fadd12c137dc
# Écrivez le programme ici
```

% TODO: Validation de l'exercice par un vu, s'il est correctement réalisé

````{solution}
```{exec} python
:name: py-ex-1-sol
:linenos:
print("Salut!")
print("Je suis élève au collège Saint-Michel.")
print("J'ai 16 ans.")
print("J'aime bien jouer au volley.")
```
````

% ### Exercice {num2}`exercice`
%
% 1. Écrivez un programme qui affiche "Bonjour tout le monde!".
% 2. Écrivez un programme qui affiche "Je programme!".
% 3. Écrivez un programme qui affiche "Je programme! Je programme!".
% 4. Écrivez un programme qui affiche "Je programme! " 10 fois de suite sans
% récrire 10 fois la même chose.
% 5. Ajoutez un commentaire qui explique ce que tu as fait au point précédent.
%
% ```{exec} python
% :editor: 4d040bd2-fe01-409f-9b82-5edd968bd23d
% # Écrivez le programme ici
% ```
%
% ````{solution}
% ```{exec} python
% :linenos:
% print("Bonjour tout le monde!")
% print("Je programme!")
% print("Je programme! Je programme!")
% # Pour répéter plusieurs fois une chaine de caractères, on peut utiliser *
% print("Je programme! " * 10)
% ```
% ````

### Exercice {num2}`exercice`

1.  Sans exécuter le programme ci-dessous, prédisez ce qu'il affichera.

```{exec} python
:linenos:
salutations = "Bonjour"
print(salutations)
print("salutations")
```

2.  Quel est l'impact des guillemets sur le mot `salutations`?

```{solution}
2.  Lorsque le mot `salutations` est écrit sans guillemets, il fait référence à
la variable. L'affichage substitue donc la variable par son contenu. Lorsque des
guillemets entourent `salutations`, alors le mot est considéré comme une chaîne
de type caractère et le mot est alors affiché tel quel.
```

### Exercice {num2}`exercice`

1.  Écrivez un programme qui permet d'effectuer les 4 opérations de base
    (addition, soustraction, multiplication et division) avec les nombres 13 et
    2 en affichant le résultat.
2.  Nous aimerions faire de même avec 10 et 3, 8 et 5, ainsi que 15 et 29.\
    Comment faire pour ne pas tout réécrire à chaque fois?\
    Notez la réponse par un commentaire dans le code.

```{exec} python
:editor: bbe7500d-5a86-4648-9701-5ccc08ddff8c
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
print(13 + 2)
print(13 - 2)
print(13 * 2)
print(13 / 2)

# Il faut utiliser des variables
a = 13              # changer la valeur de a
b = 2               # changer la valeur de b
print(a + b)
print(a - b)
print(a * b)
print(a / b)
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui permet d'afficher les calculs suivants, ainsi que la
réponse:

1. 452.52 + 27.78 =
2. 5.65 * 3.4 =
3. 4 569 - 8 532 =
4. 56 / 3 =
5. Calculer le quotient de la division entière de 345 par 37.
6. Calculer le reste de la division de 345 par 37.

```{exec} python
:editor: 13d4f2e9-0a6c-4ada-891e-8c61dd9ab1d2
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
print("452.52 + 27.78 = ", 452.52 + 27.78)
print("5.65 * 3.4 = ", 5.65 * 3.4)
print("4569 - 8532 = ", 4569 - 8532)
print("56 / 3 = ", 56 / 3)
print("Le quotient de la division entière de 345 par 37 est ", 345 // 37)
print("Le reste de la division de 345 par 37 est ", 345 % 37)
```
````

### Exercice {num2}`exercice`

Écrivez un programme qui permet de résoudre l'exercice suivant (ne pas oublier
les phrases d'explication):

1.  Luc va faire des courses. Il achète deux livres à 9.30 CHF et trois mangas à 13.50 CHF. Calculer le montant total des dépenses
    de Luc.
2.  Aline achète toujours un livre et un manga de plus que Luc. Calculer le
    montant total des dépenses de Aline.
3.  En période de soldes, tous les livres sont à 50 % et tous les
    mangas ont 6 CHF de rabais. Calculer le montant total des dépenses
    de Luc et Aline.
4.  Si Luc avait achetés 5 lires et 6 mangas, combien auraient dépensés Luc et Aline au prix normal et en rabais?

```{exec} python
:editor: 7b1c5323-09e9-4e1d-9f32-f28d9d5743d4
# Complétez le programme
prix_livre =
prix_jeu =
prix_manga =

print("Montant total des achats de Luc:", ... , "francs.")
print("Montant total des achats de Aline:", ... , "francs.")

print("Après réduction")
prix_livre =
prix_jeu =
prix_manga =

print("Montant total des achats de Luc avec réduction:", ... , "francs.")
print("Montant total des achats de Aline avec réductions:", ... , "francs.")
```

````{solution}
```{exec} python
:linenos:
prix_livre = 9.30
prix_manga = 13.50

nbre_livres_Luc = 2
nbre_manga_Luc = 3
nbre_livres_Aline = nbre_livres_Luc + 1
nbre_manga_Aline =  nbre_manga_Luc + 1

print("Montant total des achats de Luc:",
      nbre_livres_Luc * prix_livre + nbre_manga_Luc * prix_manga, "francs.")
print("Montant total des achats de Aline:",
      nbre_livres_Aline * prix_livre + nbre_manga_Aline * prix_manga, "francs.")

print("Après réduction")
prix_livre = prix_livre * 50 / 100
prix_manga = prix_manga - 6

print("Montant total des achats de Luc avec réductions:",
      nbre_livres_Luc * prix_livre + nbre_manga_Luc * prix_manga, "francs.")
print("Montant total des achats de Juliette avec réductions:",
      nbre_livres_Aline * prix_livre + nbre_manga_Aline * prix_manga, "francs.")
```
````

## Fonction input()

La fonction `input(...)` donne la main à l'utilisateur et attend que celui-ci
donne une réponse et la valide en appuyant sur {kbd}`Enter`.

La valeur saisie doit être obligatoirement affectée à une variable, sinon elle
sera perdue.

La valeur rentrée par l'utilisateur est stockée sous forme de
chaîne de caractères (de type `str`). Pour effectuer des calculs, il faut la
convertir en `int` (nombre entier) ou en `float` (nombre à virgule).

```{exec} python
:when:
nom_variable = input("...")
```

### Exemple {num2}`exemple`

```{exec} python
prenom = input("Comment t'appelles-tu?")  # prenom est une chaîne de caractères
age = int(input("Quel est ton age?"))    # age est un nombre entier
taille = float(input("Quelle est ta taille en mètres?")) # taille est un nombre à virgule
print(prenom, age, taille)
```

### Exercice {num2}`exercice`

Écrivez un programme qui demande à l'utilisateur son nom, son prénom et son année de naissance. Le programme affichera:

```{code-block} text
Quel est ton nom?
Quel est ton prénom?
En quelle année es-tu né?
Bonjour {afficher le prénom} {afficher le nom}, heureux de faire ta connaissance.
J'ai calculé ton âge, tu as {afficher l'âge } ans.
```

```{exec} python
:editor: 7bca82f8-116c-4826-9c54-4bed0bc2a8a1
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
nom = input("Quel est ton nom? ")
prenom = input("Quel est ton prénom? ")
date_de_naissance = int(input("En quelle année es-tu né? "))
age = 2026 - date_de_naissance
print("Bonjour", prenom, nom, ", heureux de faire ta connaissance.")
print("J'ai calculé ton âge, tu as ", age, " ans.")
```
````

### Exercice {num2}`exercice`

Le programme ci-dessous contient une erreur par ligne. Trouvez et corrigez-les.

```{exec} python
:editor:
print("Bienvenue dans ce nouveau programme!)
print(nombre_de_pommes = 10)
print("Vous devez payer" nombre_de_pommes * 1.5 "CHF")
print(Fin du programme)
```

````{solution}
```{exec} python
:linenos:
print("Bienvenue dans ce nouveau programme!")
nombre_de_pommes = 10
print("Vous devez payer", nombre_de_pommes * 1.5, "CHF")
print("Fin du programme")
```
````

% ### Exercice {num2}`exercice`
%
% Le programme ci-dessous devrait permettre de calculer l'année de naissance de
% l'utilisateur. Toutefois, celui-ci contient au moins une erreur par ligne.
% Trouvez et corrigez-les.
%
% ```{exec} python
% :editor:
% age = input("Quel âge as-tu? ")
% annee = input("En quelle année sommes-nous? ")
% print("Vous êtes né.e en" annee - age "ou en" annee - age - 1)
% ```
%
% ````{solution}
% ```{exec} python
% :linenos:
% age = int(input("Quel âge as-tu? "))
% annee = int(input("En quelle année sommes-nous? "))
% print("Vous êtes né.e en", annee - age, "ou en", annee - age - 1)
% ```
% ````

% ### Exercice {num2}`exercice`
%
% Écrivez un programme qui convertit des mégaoctets en bits.\
% Le programme affichera:
%
% ```{code-block} text
% Nombre de mégaoctets:
% {afficher le nombre de mégaoctets} Mo donnent {afficher le nombre de bits} bits.
% ```
%
% ```{exec} python
% :editor: 159755bc-7e41-48c4-9f88-0cc605a1929a
% # Écrivez le programme ici
% ```
%
% ````{solution}
% ```{exec} python
% :linenos:
% nb_mo = float(input("Nombre de mégaoctets: "))
% # 1 octet = 8 bits
% nb_bits = int(nb_mo * 8 * 1000000)
% print(nb_mo, "Mo donnent", nb_bits, "bits.")
% ```
% ````

### Exercice {num2}`exercice`

Le degré Fahrenheit (symbole : °F) est une unité de mesure de la température, proposée par le physicien allemand Daniel Fahrenheit en 1724. L’échelle de Fahrenheit est aujourd'hui utilisée aux États-Unis, au Bélize, aux Îles Caïman, et au Liberia.

On peut convertir une température $f$ (exprimée en Fahrenheit) en une température $c$ (exprimée en Celsius) de la façon suivante :
$$c = \frac{5}{9}\cdot (f - 32)$$

Inversement, on peut convertir une température $c$ (en Celsius) en une température $f$ (en Fahrenheit) de la façon suivante :

$$f = c \cdot \frac{9}{5} + 32$$

Le programme ci-dessous transforme une température Fahrenheit en degrés Celsius.

```{exec} python
:linenos:
f = float(input("Entrez une température en Fahrenheit: "))
c = 5/9 *(f-32)
print(f, " Fahrenheit équivalent à ", c, " Celsius")  
```

Écrivez un programme qui fait l’opération inverse pour transformer une température Celsius $c$ en degrés Fahrenheit $f$ . Vérifiez vos résultats en effectuant plusieurs conversions dans les deux sens au moyen de votre programme et du programme ci-dessus.

```{exec} python
:editor: 2fabc445-fc9f-4275-a016-aec79668c153
# Écrivez le programme ici
```

Question subsidiaire: pour quelle température a-t-on exactement le même nombre de degrés en Celsius et en Fahrenheit ($c=f$) ?

% ````{solution}
% ```{exec} python
% :linenos:
% c = float(input("Entrez une température en Celsius: "))
% f = c*9/5 +32
% print(c, "Celsius  équivalent à ", f, " Fahrenheit")  

% fahrenheit = float(input("Température en °F: "))
% celsius = (fahrenheit - 32) / 1.8
% print("Merci,", fahrenheit, "°F équivaut à", celsius, "°C")
% ```
% ````

### Exercice {num2}`exercice`
Le programme ci-dessous demande un nombre à l’utilisateur et décompose ce nombre en minutes et secondes. Testez ce programme avec quelques (petites) valeurs différentes.

```{exec} python
:editor:
nombre = int(input("Entrez un nombre de secondes : "))
secondes = nombre%60 # reste de la division par 60 => nombre de secondes
nombre = nombre//60  # division entière par 60 => minutes
minutes = nombre     # reste de la division par 60 => nombre de minutes

# affichage des résultats
print("Minutes: ", minutes)
print("Secondes: ", secondes)
```

Complétez ce programme afin qu’il affiche le nombre d’années, de jours, d’heures, de minutes et de secondes équivalents au nombre de secondes entré par l’utilisateur.

Voici quelques valeurs de références qui vous permettront de tester votre programme: 
- 86400 secondes = 1 jour
- 252914704 = 8 ans + 7 jours + 6 heures + 5 minutes + 4 secondes
- 473040000 = 15 ans

