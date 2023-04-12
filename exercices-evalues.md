# Exercices évalués

## Exercice 1

Écrire un programme en python pour réviser ses tables de multiplication. Le programme tire 2 entiers au hasard et demande à l'utilisateur le produit. On interrogera 10 fois l'utilisateur. 1 pt par bonne réponse et -1 sinon. Afficher le score.

```python
# Créé par annebi01, le 12/04/2023 en Python 3.7

import random

score = 0

for i in range(2):
    nb1 = random.randint(0,10)
    nb2 = random.randint(0,10)

    reponse = int(input(str(nb1) + " x " + str(nb2) + " = "))

    if reponse == nb1 * nb2:
        print("OK")
        score += 1 # score = score + 1
    else:
        print("KO")
        score -= 1

print("Votre score est de " + str(score) + " point(s)")
```

## Exercice 2

Initialisez deux entiers : a et b (b > a), saisis par l'utilisateur

1. Déterminiez si le nombre a est impair
2. En partant du premier impair après a, affichez tous les nombres impairs entre a et b

```python
# Créé par annebi01, le 12/04/2023 en Python 3.7

a = int(input("Choisir un nombre "))
b = int(input("Choisir un nombre supérieur au premier "))

if a % 2 == 1: # Le reste de la division de a par 2 => Modulo (%)
    # == comparaison entre a % 2 et 1
    print("Impair !")
else:
    a = a + 1 # pour avoir le premier nombre impair suivant le nombre a qui est pair

for i in range(a, b, 2): # départ, arrivé - 1, step (pas), step = 2 => 2 en 2
    print(i)
```

