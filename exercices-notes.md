# Exercices notés

## Exercices évalués

### Consignes

* Vous avez 1h30 pour réaliser les exercices suivants, dans l'ordre que vous voulez.
* Vous pouvez utiliser vos notes, vos exercices, vos cours, mais pas vos camarades.
* Vous devez faire valider chaque exercice avant de passer au suivant.

Pour ces exercices vous pouvez utiliser :

{% embed url="https://www.online-python.com/" %}

### Exercice 1

Écrire un programme en python pour réviser ses tables de multiplication. Le programme tire 2 entiers au hasard et demande à l'utilisateur le produit. On interrogera 10 fois l'utilisateur. 1 pt par bonne réponse et -1 sinon. Afficher le score.



```python
import random

score = 0
for i in range(3):
    a = random.randint(1, 10)
    b = random.randint(1, 10)
    produit_correct = a * b
    
    reponse = int(input("Combien font " + str(a) + " x " + str(b) + " ? "))
    if reponse == produit_correct:
        print("Bonne réponse !")
        score += 1
    else:
        print(f"Mauvaise réponse. La bonne réponse était " + str(produit_correct) + ".")
        score -= 1
    
print("Votre score final est : " + str(score))
```

### Exercice 2

Initialisez deux entiers : a et b (b > a), saisis par l'utilisateur :

1. Déterminiez si le nombre a est impair
2. En partant du premier impair après a, affichez tous les nombres impairs entre a et b



```python
# Saisir les valeurs de a et b
a = int(input("Entrez la valeur de a : "))
b = int(input("Entrez la valeur de b (b doit être supérieur à a) : "))

# Déterminer si a est impair
if a % 2 != 0:
    print(a, " est impair.")
else:
    print(a, " est pair.")
    a += 1

# Afficher tous les nombres impairs entre a et b
print("Les nombres impairs entre a et b sont :")
for i in range(a, b, 2):
    print(i)
```

### Exercice 3

Compter les voyelles dans une chaîne de caractères : Écrivez une fonction qui prend une chaîne de caractères en entrée et retourne le nombre de voyelles qu'elle contient.

Exemple d'entrée : "Bonjour" Sortie attendue : 3

### Exercice 4

Écrivez une fonction qui prend une température en degrés Celsius en entrée et la convertit en degrés Fahrenheit en utilisant la formule : F = (C \* 9/5) + 32.

Exemple d'entrée : 20 Sortie attendue : 68.0

### Exercice 5

Nous avons vu les fonctions dans le cadre de Tkinter, serez vous réutiliser le concept ici.

Écrivez une fonction qui prend une liste de nombres en entrée (saisis un par un) et retourne la moyenne de ces nombres.
