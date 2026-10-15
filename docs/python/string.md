% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Les chaînes de caractères

En Python, on peut stocker et manipuler du texte au moyen d'une **chaîne de caractères** (ou **string**)(type `str`).
Une **chaîne de caractères** se définit comme une suite de caractères entourée de guillemets simples ('...') ou guillemets doubles ("...").

Une  **chaîne de caractères** ressemble à une liste de caractères: on peut accéder à ses caractères au moyen de leurs index. Mais à la différence d'une liste, une chaîne est une *séquence immuable* : on ne peut pas la modifier directement (si faut modifier une chaîne de caractère, on doit en créer une nouvelle copie).

```{exec} python
texte = "Hello"
liste = ['H', 'e', 'l', 'l', 'o']

# Les deux permettent l'indexation
print(texte[0])  # H
print(liste[0])  # H

# On peut modifier une liste
liste[0] = 'h'
print(liste)  # ['h', 'e', 'l', 'l', 'o']

# Mais on ne peut pas modifier une chaîne directement
try:
    texte[0] = 'h'  # produit un message d'erreur !
except TypeError as e:
    print(e)

```

## Création d'une chaîne de caractères

Une chaîne de caractères est déclarée par une suite de caractères entre guillemets simples ou doubles.

### Exemple {num2}`exemple`

```{exec} python
:editor:
nom = "Dupont"
prenom = 'Jean'

print("Bonjour", prenom , nom)
```

Il est aussi possible de définir une chaîne de caractères vide. Il suffit d'écrire uniquement les guillemets sans rien à l'intérieur.

```{exec} python
:linenos:
:when:
mon_texte = ""
```

## Accès aux caractères d'une chaîne

On peut accéder à chaque élément d'une chaîne de caractères au moyen de son **index**. L'index d'un caractère correspond à sa position dans la chaîne en partant de 0 depuis la gauche.

- `mot[i]` pour accéder au caractère à l'index `i` (avec `i` allant de 0 à la longeur du mot-1)
- `mot[i:j]` pour accéder aux caractères compris entre les index `i` et `j-1`

```{tip}
Il est également possible de mettre un index négatif, ce qui correspond à calculer l'index depuis la fin du mot (depuis la gauche).

`mot[-1]` correspond ainsi au dernier caractère, `mot[-2]` à l'avant dernier, etc...
```

### Exemple {num2}`exemple`
| mot | f   | r  | a   | i   | s   | e   |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| index | **0** | **1** | **2** | **3** | **4** | **5** |

```{exec} python
:editor:
mot = "fraise"

print(mot[0]) # f
print(mot[4]) # s
print(mot[-1]) # e
print(mot[1:3]) # ra
print(mot[2:-1]) # ais    affiche jusqu'à l'avant-dernier caractère (dernier -1)
```

### Exercice {num2}`exercice`

Sans l'exécuter, déterminez ce que va afficher le programme suivant. Ensuite, exécutez-le pour vérifier votre réponse.
```{exec} python
:editor:
mot = "domicile et parasol."

print(mot[0]) 
print(mot[2]) 
print(mot[-1])
print(mot[7:10])
print(mot[0:2], mot[2:4], mot[-4:-1]) 
```

## Opérations de base sur les chaînes de caractères 
- La longeur d'une chaîne de caractères s'obtient au moyen de la fonction `len()`
```{exec} python
:editor:
mot1 = "abc"
mot2 = "fraise"
print(mot1.len())		   # affiche 3
print(mot2.len())		   # affiche 6
```

- La concaténation, c’est-à-dire la mise bout à bout de deux chaînes, s’effectue à l’aide de l’opérateur +
```{exec} python
:editor:
mot1 = "para"
mot2 = "pluie"
mot3 = mot1 + mot2 # concatène les 2 mots dans mot3
print(mot3)		   # affiche "parapluie"
```

### Exercice {num2}`exercice`

Sans l'exécuter, déterminez ce que va afficher le programme suivant. Ensuite, exécutez-le pour vérifier votre réponse.
```{exec} python
:editor:
# Contrepétrie 1
str1 = "un pain de glace" 
str2 =str1[0:3]+str1[11]+str1[4:11] +str1[3]+str1[12:]
print(str2)
```

### Exercice {num2}`exercice`

Sans l'exécuter, déterminez ce que va afficher le programme suivant. Ensuite, exécutez-le pour vérifier votre réponse.
```{exec} python
:editor:
# Contrepétrie 2
str1 = "un champ de coton"

str2 = str1[0:3]+str1[14]+str1[5:14]+str1[3:5]+str1[15:]
print(str2)
```

## Fonctions de traitement des chaînes de caractères 
Le langage Python propose de nombreuses fonctions pour la gestion des chaînes de caractères. Voici les principales:

- `ch.find(txt)`: indique la position de la sous-chaine `txt` 
- `ch.count(txt)`: renvoie le nombre de fois où `txt` est présent dans la chaine `ch`.
- `ch.replace(txt1, txt2)`: renvoie une nouvelle chaine dans laquelle chaque occurrence de `txt1` est remplacée par `txt2`
- `ch.upper()`: renvoie le texte de la chaine de caractères `ch` en majuscules
- `ch.lower()`: renvoie le texte de la chaine de caractères `ch` en minuscules

Rappel: une chaîne de caractère est une variable immuable, et n'est pas modifiée lors de l'appel de ces fonctions. Par contre certaines de ces fonctions (`replace`, `upper` et `lower` par exemple) retournent une nouvelle chaîne de caractères que l'on peut récupérer en affectant la valeur de retour à une nouvelle variable.

### Exemple {num2}`exemple`
```{exec} python
:editor:
monTexte = "mon chien s'appelle Ben"

pos = monTexte.find("chi")
print(pos)      # affiche 4, puisque le texte "chi" 
                # se trouve au rang 4 de la variable monTexte

nbre = monTexte.count("en")
print(nbre)	# affiche 2, puisqu’on trouve 2x "en" dans monTexte

txt2 = monTexte.replace("chien", "chat")
print(txt2)     # affiche "mon chat s'appelle Ben"
```

### Exemple {num2}`exemple`
```{exec} python
:editor:
minMaj = " JE suis un MELANGE de Minuscules et MajusCules"

maj = minMaj.upper()
print(maj)		# affiche: JE SUIS UN MELANGE DE MINUSCULES ET MAJUSCULES

min = minMaj.lower()
print(min)	     # affiche: je suis un melange de minuscules et majuscules
```

### Exercice {num2}`exercice`
Ecrire un programme qui demande une lettre, puis une phrase à l’utilisateur. Le programme compte ensuite le nombre de fois où cette lettre apparait dans la phrase.
```{exec} python
:editor: 6771344a-1dd8-4816-bb25-78b9e8e1e71b
# Écrivez le programme ici

```

````{solution}
```{exec} python
mot = input("Donne-moi un mot: ")
lettre = input("Donne-moi une lettre: ")

compteur = mot.count(lettre)
 
print("La lettre ", lettre, "apparait", compteur, "fois dans le mot", mot)

```
````

### Exercice {num2}`exercice`

Reprenons l'exercice que l'on a fait dans le chapitre *Boucle while*. 
Complétez le programme pour qu'il demande à l'utilisateur la capitale de la
Suisse. Tant que la réponse n'est pas "Berne", le programme redemande une
nouvelle réponse.
Mais cette fois-ci, le programme doit ne pas tenir compte de la casse (minuscule/majuscule) et accepter ainsi diférentes réponses: *Berne*, *BERNE*, *berne*, *beRNe* ...
 
Exemple d'exécution:

```{code-block} text
Quelle est la capitale de la Suisse?
Zurich
Faux, essaie encore!
Genève
Faux, essaie encore!
BErnE
Bravo!
```

```{exec} python
:editor: c5bf6458-d3df-4458-bb42-7e7fdeb8125c
capitale = input("Quelle est la capitale de la Suisse?")

# Complétez le programme ici
while ...:
  capitale = input("Faux, essaie encore!")
print("Bravo!")
```

````{solution}
```{exec} python
:linenos:
capitale = input("Quelle est la capitale de la Suisse?")

while capitale.upper() != "Berne".upper():
  capitale = input("Faux, essaie encore!")
print("Bravo!")
```
````

## Parcours d'une chaîne de caractères

On peut parcourir tous les caractères d'une chaîne de caractères de la même manière que les éléments d'une liste.

- au moyen de leurs index:
```{exec} python
:editor:
chaine = "Bonjour!"
for i in range(len(chaine)):
    print(chaine[i])
```
- en parcourant directement les caractères individuellement:
```{exec} python
:editor:
chaine = "Bonjour!"
for lettre in chaine:
    print(lettre)
```

### Exemple {num2}`exemple`
Ce programme parcours tous les caractères d'un texte afin d'échanger toutes les voyelles par une même voyelle.
```{exec} python
:editor:
voyelles='aeiou'
nouvelleVoyelle = 'o' # vous pouvez modifier ici la voyelle de remplacement

texteOriginal = "Buvons un coup ma serpette est perdue!"

# Création d'une nouvelle chaîne de caractères vide. Cette chaîne 
# va nous servir à créer le nouveau texte, caractère par caractère
nouveauTexte = ""	

for lettre in texteOriginal:
    if lettre in voyelles:
      nouveauTexte += nouvelleVoyelle  
    else:
       nouveauTexte+= lettre
print(nouveauTexte)
```

### Exercice {num2}`exercice`
Définissez une fonction `supprimeEspace()` qui reçoit une chaîne de caractère en entrée et retourne une nouvelle chaîne dans lesquels tous les espaces ont été supprimés.
```{exec} python
:editor: 6371344a-1dd8-4816-bb25-78b9e8e1e71b
# Complétez ce programme en définissant la fonction supprimeEspace()
test = " abc def g  hi jkl mn o  pqrst uv w xyz"

nouveauTexte = supprimeEspace(test)

# ceci doit afficher "abcdefghijklmnopqrstuvwxyz"
print("J'ai supprimé", len(test)-len(nouveauTexte), "espaces: ", nouveauTexte) 
```

````{solution}
```{exec} python
def supprimeEspace(texte):
    nouveauTexte = ""
    for lettre in texte:
        if lettre !=" " :
            nouveauTexte+= lettre
    return nouveauTexte
	
test = " abc def g  hi jkl mn o  pqrst uv w xyz"

nouveauTexte = supprimeEspace(test)
print("J'ai supprimé", len(test)-len(nouveauTexte), "espaces: ", nouveauTexte)

# Deuxième version :
def supprimeEspace2(texte):
    nouveauTexte = texte.replace(" ", "")
    return nouveauTexte

nouveauTexte = supprimeEspace2(test)
print("J'ai supprimé", len(test)-len(nouveauTexte), "espaces: ", nouveauTexte)

```
````

### Exercice {num2}`exercice`
Ecrire un programme qui calcule la distance de Hamming entre 2 mots de même longueur.

- Ecrire une fonction qui calcule la distance de Hamming entre 2 mots reçus en paramètre. Testez et validez votre fonction avec plusieurs paires de mots.
- Demandez 2 mots (de même longeur) à l'utilisateur. Tant que les 2 mots ne sont pas de même longueur, le programme doit redemander les 2 mots.
- Calculez leur distance de Hamming en appelant la fonction

Pour rappel, la distance de Hamming entre deux mots de même longueur est le nombre de positions pour lesquelles les caractères correspondants diffèrent.
- La distance de Hamming entre *CORDE* et *PORTE* vaut 2
- La distance de Hamming entre *LOUP* et *coup* vaut 1

```{exec} python
:editor: 6371661b-1dd8-4016-bb25-78b9e8e1e71b
# Écrivez le programme ici

```

Option: demandez à l'utilisateur si il faut prendre en compte la casse (minuscules/majuscules). L'utilisateur devra répondre par O ou N, et le programme effectuera le calcul de la distance de Hamming en conséquence.

````{solution}
```{exec} python
# calcul de la distance de Hamming pour 2 mots de même longueur 
# en prenant en compte la casse
def distance_Hamming(mot1, mot2):
    distance = 0
    for i in range(len(mot1)):
        if mot1[i] != mot2[i]:
            distance += 1
    return distance
            
mot1=""
mot2=" " # mot1 et mot2 sont initialisés de sorte que l'on rentre dans la boucle la 1ère fois

while len(mot1) != len(mot2): 
    print("Nous allons calculer la distance de Hamming entre 2 mots de même longueur")
    mot1 = input("1er mot? ")
    mot2 = input("2e mot? ")

dist = distance_Hamming(mot1, mot2)
print("La distance entre", mot1,"et", mot2, "est de", dist)

```

```{exec} python
# calcul de la distance de Hamming pour 2 mots de même longueur 
# en ignorant la casse
def distance_Hamming(mot1, mot2):
    distance = 0
    for i in range(len(mot1)):
        if mot1[i] != mot2[i]:
            distance += 1
    return distance
            
mot1=""
mot2=" " # mot1 et mot2 sont initialisés de sorte que l'on rentre dans la boucle la 1ère fois

while len(mot1) != len(mot2): 
    print("Nous allons calculer la distance de Hamming entre 2 mots de même longueur")
    mot1 = input("1er mot? ")
    mot2 = input("2e mot? ")

casse = input("VOulez-vous prendre en compte la casse? (O/N)")
if casse.upper()=="N" :
   mot1 = mot1.upper()
   mot2 = mot2.upper()

dist = distance_Hamming(mot1, mot2)
print("La distance entre", mot1,"et", mot2, "est de", dist)
```
````

### Exercice {num2}`exercice`
Ecrire un programme qui demande un mot à l’utilisateur, puis qui affiche ce mot, en insérant une étoile entre chaque caractère (mais pas au début ni à la fin du mot !).

Exemple : si l’utilisateur écrit *Bonjour*, le programme affichera :	*B\*o\*n\*j\*o\*u\*r*
```{exec} python
:editor: 6371514a-1dd8-4816-bb25-78b9e8e1e71b
# Écrivez le programme ici

```

````{tip}
:class: dropdown
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

````{solution}
```{exec} python
mot = input("Ecris un mot: ")
nouveauMot=mot[0]
for i in range(1,len(mot)):
    nouveauMot+="*"+mot[i]
print(nouveauMot)

```
````

### Exercice {num2}`exercice`
Ecrire une fonction `verlan(mot)` qui reçoit un mot en argument et renvoie ce mot à l'envers.

Exemple : si l’utilisateur écrit `verlan("Wagon")`, la fonction va retourner le mot *nogaW*.
```{exec} python
:editor: 6371516a-1dd8-4816-bb25-78b9e8e1e71b
# Écrivez le programme ici

```

````{solution}
```{exec} python
texteOriginal = input("Ecirs un mot: ")

nouveauTexte = ""
for lettre in texteOriginal:
       nouveauTexte = lettre+nouveauTexte
print("Voici ", texteOriginal, "en verlan: ", nouveauTexte)
```
````

### Exercice {num2}`exercice`
Ecrire un programme qui demande un mot à l’utilisateur, puis vérifie si ce mot est un palindrome ou non.
Un palindrome est un mot (ou un texte) dont l'ordre des lettres reste le même qu'on le lise de gauche à droite ou de droite à gauche. 

Exemples de palindromes :  Bob, kayak, radar, selles, ressasser…

```{tip}
:class: dropdown
Il faut utiliser une boucle pour parcourir le mot et vérifier que : 
- le caractère N°0 est égal au caractère N°-1
- le caractère N°1 est égal au caractère N°-2
- ...

on peut optimiser en ne parcourant que la première moitié des caractères en les comparant chaque ois avec les caractères de la 2e moitié du mot.
```

```{exec} python
:editor: 6371515a-1dd8-4816-bb25-78b9e8e1e71b
# Écrivez le programme ici

```
 