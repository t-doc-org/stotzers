% Copyright 2024 Caroline Blank <caro@c-space.org>
% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Boucle while

## Répétition d'un bloc d'instructions

La boucle while (qui signifie "tant que" en anglais) permet de répéter un bloc
d'instructions tant qu'une condition est vraie.

```{exec} python
:when:
while condition:
  instruction 1
  instruction 2
  ...
```

```{important}
En Python, les instructions appartenant à un même **bloc d'instructions** sont reconnaissables car elles ont toutes exactement la même **indentation**.
```

````{list-grid}
:style: grid-template-columns: 1fr 1fr;
- # Programme
  ```{exec} python
  :editor:
  nb_points = 0
  max = 10
  while nb_points < max:
    print("Points:", nb_points)
    nb_points += 3
  print("Bravo!")
  ```
- # Ordinogramme
  ```{figure} images/while.png
  :alt: Ordinogramme boucle for
  ```
````

La boucle `while` peut être utilisée comme une boucle `for`. Pour cela, il faut
définir un compteur qui va "compter" le nombre de répétitions.

````{list-grid}
:style: grid-template-columns: 1fr 1fr;
- # Boucle for
  ```{exec} python
  :editor:
  for _ in range(10):
    print("Hello")
  ```
- # Boucle while
  ```{exec} python
  :editor:
  compteur = 0
  while compteur < 10:
    print("Hello")
    compteur += 1
  ```
````

```{important}
Si on utilise un compteur dans la condition du while, il ne faut pas oublier d'incrémenter (augmenter) ce compteur à chaque passage
dans la boucle, sinon la condition sera toujours vraie et la boucle ne 
s'arrêtera jamais (boucle infinie). Cela fait "planter" le programme.
```

### Exercice {num2}`exercice`

Sans l'exécuter, qu'affiche ce programme?

Ensuite, exécutez le programme pour vérifier votre réponse.

```{exec} python
:editor:
i = 1
while i <= 10:
  print("7 *", i, "=", 7 * i)
  i = i + 1
```

```{solution}
Ce programme calcule et affiche le livret de 7 de 1 à 10.
```

### Exercice {num2}`exercice`

Sans l'exécuter, qu'affiche ce programme?

Ensuite, exécutez le programme pour vérifier votre réponse.

```{exec} python
:editor:
n = 2
while n <= 50:
  print(n)
  n = n + 2
```

```{solution}
Ce programme affiche les nombres paires de 2 à 50 compris.
```

### Exercice {num2}`exercice`

Sans exécuter le programme, qu'affichera-t-il?

```{exec} python
:editor:
s = 0
i = 1
while i <= 5:
  s = s + i
  i = i + 1
print(s)
```

```{solution}
| ligne | condition (while) | s   | i   | print |
| :---: | :---------------: | :-: | :-: | :---: |
| 1 |              | 0   | ?   |  |
| 2 |              | 0   | 1   |  |
| 3 | 1 <= 5: Vrai | 0   | 1   |  |
| 4 |              | 1   | 1   |  |
| 5 |              | 1   | 2   |  |
| 3 | 2 <= 5: Vrai | 1   | 2   |  |
| 4 |              | 3   | 2   |  |
| 5 |              | 3   | 3   |  |
| 3 | 3 <= 5: Vrai | 3   | 3   |  |
| 4 |              | 6   | 3   |  |
| 5 |              | 6   | 4   |  |
| 3 | 4 <= 5: Vrai | 6   | 4   |  |
| 4 |              | 10  | 4   |  |
| 5 |              | 10  | 5   |  |
| 3 | 5 <= 5: Vrai | 10  | 5   |  |
| 4 |              | 15  | 5   |  |
| 5 |              | 15  | 6   |  |
| 3 | 6 <= 5: Faux | 15  | 6   |  |
| 6 |              | 15  | 6   | 15 |

Le programme affichera 15.
```

### Exercice {num2}`exercice`

En utilisant une boucle `while`, écrivez un programme qui:
- affiche tous les nombres entiers jusqu'à 15,
- à la fin, affiche "J'ai fini de compter!".

```{exec} python
:editor: ac83f5a3-c948-4491-b540-dc0d10402745
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
i = 1
while i <= 15:
  print(i)
  i += 1
print("J'ai fini de compter!")
```
````

### Exercice {num2}`exercice`

En utilisant une boucle `while`, écrivez un programme qui:
- demande un nombre entier à l'utilisateur,
- affiche les 5 premiers multiples de ce nombre.

```{exec} python
:editor: b5720432-d84a-4e5a-a1b6-121bdaea31a7
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
nombre = int(input("Choisissez un nombre: "))
i = 1
while i <= 5:
  print(i * nombre)
  i += 1
```
````

### Exercice {num2}`exercice`

Complétez le programme pour qu'il demande à l'utilisateur la capitale de la
Suisse. Tant que la réponse n'est pas "Berne", le programme redemande une
nouvelle réponse.

Exemple d'exécution:

```{code-block} text
Quelle est la capitale de la Suisse?
Zurich
Faux, essaie encore!
Genève
Faux, essaie encore!
Berne
Bravo!
```

```{exec} python
:editor: c5bf6458-d3df-4458-bb42-6e6edeb8125c
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
	
while capitale != "Berne":
  capitale = input("Faux, essaie encore!")
print("Bravo!")
```
````

### Exercice {num2}`exercice`

Tout d'abord, sans les exécuter, expliquez la différence entre les deux
programmes. Ensuite, testez-les pour vérifier votre réponse.

````{list-grid}
:style: grid-template-columns: 1fr 1fr;
- # Programme 1
  ```{exec} python
  :editor:
  n = 5
  if n < 10:
    n += 1
    print(n)
  ```
- # Programme 2
  ```{exec} python
  :editor:
  n = 5
  while n < 10:
    n += 1
    print(n)
  ```
````

```{solution}
Le programme 1 affichera:
6

Le programme 2 affichera:
6
7
8
9
10

Avec un `if` le condition est testée une seule fois, le bloc d'instructions est
lui aussi exécuté une seule fois, alors qu'avec le `while`, le bloc
d'intructions sera exécuté tant que la condition `n < 10` est vérifiée.
```

### Exercice {num2}`exercice`

Déterminez ce qu'affichera le programme suivant.

```{exec} python
:linenos:
x = 0
y = 20
while x < y:
  y -= x * 2
  x = x + 2
  print(x + y)
```

```{solution}
| ligne | condition (while) | x  | y  | print |
| :---: | :-------: | :-:| :-:| :---: |
| 1 |              | 0  | ?  |  |
| 2 |              | 0  | 20 |  |
| 3 | 0 < 20: vrai | 0  | 20 |  |
| 4 |              | 0  | 20 |  |
| 5 |              | 2  | 20 |  |
| 6 |              | 2  | 20 | 22 |
| 3 | 2 < 20: vrai | 0  | 20 |  |
| 4 |              | 2  | 16 |  |
| 5 |              | 4  | 16 |  |
| 6 |              | 4  | 16 | 20 |
| 3 | 4 < 16: vrai | 4  | 16 |  |
| 4 |              | 4  | 8  |  |
| 5 |              | 6  | 8  |  |
| 6 |              | 6  | 8 | 14 |
| 3 | 6 < 8: vrai  | 6  | 8  |  |
| 4 |              | 6  | -4 |  |
| 5 |              | 8  | -4 |  |
| 6 |              | 8  | -4 | 4 |
| 3 | 8 < -4: faux | 8  | -4 |  |
```

### Exercice {num2}`exercice`
Implémentez l'algorithme d'Euclide qui permet de déterminer le PGDC de 2 nombres donnés par l'utilisateur.
L'algorithme d'Euclide est décrit par un ordinogramme au début du chapitre [Algorithme](./algorithme.md).
```{exec} python
:editor: 7ff640be-fd71-493b-bb0c-f7c495af9ac3
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
# Implémentation de l'algorithme d'Euclide pour déterminer le PGDC
a = int(input("Entrez un 1er nombre entier: "))
b = int(input("Entrez un 2e nombre entier: "))

r = a%b
while r!=0:
   a = b
   b = r
   r = a%b
print("Le PGDC est", b)
```
````

### Exercice {num2}`exercice`

Vous achetez un scooter à 3'500 CHF avec un crédit dont le taux annuel est de 9%.
Vous pouvez rembourser 100 CHF par mois (intérêts compris).

- Combien de mensualités sont nécessaires pour rembourser la totalité du montant?
- Quel sera le montant total que vous aurez alors payé?

````{tab-set}
:sync-group: etape
```{tab-item} Étape 1
:sync: etape1
Afin de faciliter la lecture du programme, définissez une variable pour chacun des paramètres de cet exercice: prix, dette, taux d'intérêt, nombre de mensualités ...
```

```{tab-item} Étape 2
:sync: etape1
Calculez également le taux d'intérêt mensuel puisque la simulation va se faire mois par mois et qu'il faudra donc recalculer les intérêts mois par mois.
Le taux d'intérêt mensuel correspond au douzième du taux d'intérêt annuel.
```

```{tab-item} Étape 3
:sync: etape2
Créez une boucle qui s'exécutera tant que la dette ne sera pas totalement remboursée.
```

```{tab-item} Étape 4
:sync: etape3
Chaque passage dans la boucle correspond à un mois. Il faut donc mettre à jour les différentes variables à chaque passage dans la boucle.
```

```{tab-item} Étape 5
:sync: etape3
Faites quelques autres simulations de remboursement en changeant les paramètres de votre programme (durée, prix...)
```
````
```{exec} python
:editor: dca83242-8a76-44d3-8dee-46815635908a
# Écrivez le programme ici
```

````{solution}
```{exec} python
:linenos:
dette = 3500
tauxAnnuel = 9 / 100
tauxMensuel = tauxAnnuel / 12
remboursement = 100
montantRembourse = 0
nb_mensualites = 0
while dette > 0:
  dette += dette * tauxMensuel
  nb_mensualites += 1
  if dette >= remboursement:
    dette -= remboursement
    montantRembourse += remboursement
    print("Dette après", nb_mensualites, "mois: ", dette, "CHF.")
  else:
    print("Le dernier versement sera de", dette, "CHF.")
    montantRembourse += dette
    dette = 0

print("Nombre de mensualités nécessaires pour rembourser la dette:", nb_mensualites)
print("Montant payé au total: ", montantRembourse)
```
````
