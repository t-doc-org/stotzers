% Copyright 2024 Caroline Blank <caro@c-space.org>
% Copyright 2026 Sylvain Stotzer <sylvain.stotzer@edufr.ch>
% SPDX-License-Identifier: CC-BY-NC-SA-4.0

# Opérateurs 

## Opérateurs mathématiques

Les opérateurs mathématiques permettent de faire des calculs simples avec les
nombres.

| Opérateur | Nom                                   | Exemple | Résultat |
| :-------: | :-----------------------------------: | :-----: | :------: |
| +         | Addition                              | 3 + 4   | 7        |
| -         | Soustraction                          | 9 - 12  | -3       |
| *         | Multiplication                        | 5 * 6   | 30       |
| /         | Division                              | 11 / 2  | 5.5      |
| **        | Puissance                             | 2 ** 3  | 8        |
| //        | Division entière                      | 26 // 6 | 4        |
| %         | Modulo (reste de la division entière) | 26 mod 6| 2        |


### Exercice {num2}`exercice`

Quel est le résultat des expressions suivantes en Python?

```{role} input(quiz-input)
:right: width: 5rem;
:check: json trim
```

```{quiz}
:style: max-width: 30rem;
1.  {input}`{"2.4": true,
             "2,4": "En Python, il faut utiliser un point pour les nombres à
                     virgule."}`
    {quiz-hint}`Il faut effectuer la division.`
    `12 / 5`
2.  {input}`{"3": true}`
    {quiz-hint}`Il faut effectuer la division entière de 15 par 4.`
    `15 // 4`
3.  {input}`{"3": true}`
    {quiz-hint}`% est le reste de la division entière.`
    `18 % 5`
4.  {input}`{"1": true}`
    {quiz-hint}`% est le reste de la division entière.`
    `17'245 % 2`
```

## Opérateurs de comparaison

Les opérateurs de comparaison permettent de comparer deux valeurs entre elles.
Le résultat de la comparaison est de type booléen: True ou False.

| Opérateur | Nom                  | Exemple | Résultat |
| :-------: | :------------------: | :-----: | :------: |
| ==        | égal à               | 3 == 7  | False    |
| !=        | différent de         | 3 != 7  | True     |
| >         | plus grand que       | 3 > 7   | False    |
| <         | plus petit que       | 3 < 7   | True     |
| >=        | plus grand ou égal à | 3 >= 7  | False    |
| <=        | plus petit ou égal à | 3 <= 7  | True     |

### Exercice {num2}`exercice`

Est-ce que les expressions suivantes sont `True` (vrai) ou `False` (faux)?

```{role} select(quiz-select)
:right:
:options: |
: True
: False
```

```{quiz}
:style: max-width: 25rem;
1.  {select}`True`  `1 + 1 == 2`
2.  {select}`False` `2 * 3 == 3`
3.  {select}`True`  `2 + 3 != 4`
4.  {select}`False` `14 >= 15`
5.  {select}`False` `2 ** 3 == 6`
6.  {select}`True`  `13 >= 13`
```

## Opérateurs logiques

Les opérateurs logiques permettent de combiner plusieurs conditions simples

| Opérateur | Description          |
| :-------: | :------------------: |
| and       | retourne `True` si les deux conditions sont vraies |
| or        | retourne `True` si une des conditions est vraie    |
| not       | inverse le résultat: renvoie `True` si le résultat l'entrée est `False` et vice-versa |

### Exemple {num2}`exemple`

`(5 < 3) and (2 < 6)` retourne `False`, car `5 < 3` retourne `False`.

`(5 < 3) or (2 < 6)` retourne `True`, car `2 < 6` retourne `True`.

`(2 < 3) and (2 < 6)` retourne `True`, car `2 < 3` retourne `True` et `2 < 6`
retourne `True`.

`(2 > 3) or (2 > 6)` retourne `False`, car `2 > 3` retourne `False` et `2 > 6`
retourne `False`.

`not (4 == 4)` retourne `False`, car `4 == 4` retourne `True`.

`not (3 == 4)` retourne `True`, car `3 == 4` retourne `False`.

### Exercice {num2}`exercice`

Est-ce que les expressions suivantes sont `True` (vrai) ou `False` (faux)?

```{role} select(quiz-select)
:right:
:options: |
: True
: False
```

```{quiz}
:style: max-width: 40rem;
1.  {select}`False`  `(3 < 3) or (10 < 6)`
2.  {select}`False`  `(0 < 3) and (5 < 5)`
3.  {select}`True`   `(1 < 5) and (5 > 2)`
4.  {select}`True`  `True and True`
5.  {select}`True` `(True and False) == (False and True)`
6.  {select}`True` `(False or False) == (True and False)`
7.  {select}`False` `not(True)`
8.  {select}`True`  `not(not(True))`
9.  {select}`True`  `not(not(not(False)))`
10.  {select}`True`  `not(False or False)`
```

## Priorité des opérateurs

La priorité détermine l’ordre dans lequel les opérateurs sont appliquées aux opérandes. Les règles de priorité des opérateurs en Python sont les mêmes qu'en mathématiques. Dans le tableau suivant, les opérateurs sont présentés du plus au moins prioritaire. A priorité égale (lorsque 2 opérateurs sont sur une ême ligne), les opérateurs d’une expression sont appliqués de gauche à droite. 

| Opérateurs | Symboles Python |
| :-------: | :-------: |
| Parenthèse | ( ) |
| Puissance | ** |
| Négation arithmétique | - |
| Multiplication et division | * {hspace}`1em` /  {hspace}`1em` // {hspace}`1em`  % |
| Addition et soustraction | + {hspace}`1em` -  |
| Opérateurs de comparaison | < {hspace}`1em` <= {hspace}`1em` > {hspace}`1em`  >= {hspace}`1em` != {hspace}`1em` == |
| ET logique | and
| OU logique | or

### Exemple {num2}`exemple`

`6+2**3/2` vaut `10`, car on effectue les opérations dans l'ordre suivant: 

`6+2**3/2 = 6+8/2 = 6+4 = 10`

#### Remarque
Les parenthèses servent à préciser la priorité des calculs dans une expression et à éviter toute ambiguïté. Il ne faut pas hésiter à les utiliser!
L'exemple ci-dessus peut être réécrit avec des parenthèses pour éviter toute ambiguïté. 

 `6+2**3/2 = 6+((2**3)/2)` 

### Exercice {num2}`exercice`

Quel est le résultat des expressions suivantes en Python?

```{role} input(quiz-input)
:right: width: 5rem;
:check: json trim
```

```{quiz}
:style: max-width: 30rem;
1.  {input}`{"4": true}`
    {quiz-hint}`Il faut effectuer les opérations de gauche à droite.`
    `(1+2-3+4)`
2.  {input}`{"-2": true,
             "2": "En Python, l'ordre de priorité est le même qu'en maths."}`
    `4 - 3 * 2`
3.  {input}`{"11": true}`
    {quiz-hint}`Il faut effectuer tout d'abord la division et la multiplication avant de faire l'addition.`
    `6/2+2*4`
4.  {input}`{"75": true}`
    {quiz-hint}`Il faut effectuer tout d'abord la parenthèse, puis la puissance.`
    `(2 + 3) ** 2 * 3`
5.  {input}`{"29": true}`
    {quiz-hint}`Il faut effectuer tout d'abord la puissance.`
    `2 + 3 ** 2 * 3`
5.  {input}`{"8": true}`
    {quiz-hint}`Tous ces opérateurs ont la même priorité !`
	`2*10%3*4`
6.  {input}`{"False": true,
             "false": "En Python, il faut mettre une majuscule aux valeurs booééennes True et False."}`
    {quiz-hint}`Il faut effectuer les comparaisons avant l'opérateur logique.`
    `15 > 3 and 10 < 3 `
7.  {input}`{"True": true,
             "true": "En Python, il faut mettre une majuscule aux  valeurs booééennes True et False."}`
    {quiz-hint}`Il faut effectuer les comparaisons avant l'opérateur logique.`
    `15 > 3 or 10 < 3 `  
```
Si nécessaire, vous pouvez vérifier vos calculs au moyen de la console qui se trouve au bas de la page.

### Exercice {num2}`exercice`

Quelle est la valeur des expressions suivantes ? Déterminer ceci de tête ou sur papier.

{.num-paren .vsep-1}
1.  `3 + 2 == 18 / 3`
2. `-5 ** 2 + 4 + 3 ** 2`
3. `2 * 10 % 3 * 4`
4. `10 < 5 and  5 < 1 or 2 < 5`
5.  `27 % 5 != 41 % 5`
6. `(2**2==4) and ((-2)**2==4)`
7. `False or True == False`
8. `False or False == False or True`

Vérifier ensuite vos réponses au moyen de la console ci-desous:

<iframe src="https://pyodide.org/en/stable/console.html" width="800" height="400"></iframe>

