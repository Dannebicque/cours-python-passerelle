# Séance 1

## Les tests

Un premier exemple d'un test avec python :

```python
age = 12
if age < 18:
    print("Cette personne est mineure")
else:
    print("Cette personne est majeure")

```

Vous noterez que l'instruction print() permet d'afficher quelque chose à l'écran. On peut aussi utiliser la fonction input() pour demander à l'utilisateur de saisir quelque chose. Et modifier le code ci-dessus pour demander l'âge à l'utilisateur.


```python
age = int(input("Quel est votre âge ? "))
if age < 18:
    print("Cette personne est mineure")
else:
    print("Cette personne est majeure")
```

## Exercices avec les tests : Le Chifoumi

Le chifoumi est un jeu de mains qui se joue à deux. Chaque joueur choisit entre pierre, feuille et ciseaux. Le gagnant est celui qui a choisi le plus fort des trois.​
* La pierre bat les ciseaux​
* La feuille bat la pierre​
* Les ciseaux battent la feuille​
* Si les deux joueurs choisissent le même élément, c'est un match nul​

Ecrire un programme qui demande à l'utilisateur de saisir son choix, et qui affiche le résultat du chifoumi. Le deuxième joueur est géré par l'ordinateur​
* On peut utiliser la fonction random.randint() pour générer un nombre aléatoire entre 0 et 2., et considérer que 0 = pierre, 1 = feuille, 2 = ciseaux.​

```python
import random

choix = int(input("Choisissez entre pierre (0), feuille (1) ou ciseaux (2) : "))
choixOrdi = random.randint(0, 2)

... A vous de compléter le code
```

## La boucle "pour"

Dans cette boucle particulière on connait le nombre d’itération de notre boucle. On sait que la boucle doit varier entre deux valeurs.​

* Elle peut se lire « pour i entre 1 et 10 » alors…​
* Tant que la variable i est comprise entre 1 et 10 la boucle exécute le traitement « vrai » et augmente automatiquement la boucle de 1 (ou d’un pas défini). Si i est plus grand que 10, alors la boucle s’arrête.​

## Exercices avec la boucle pour

Pour chaque exercice, écrire l'algorigramme, et coder en python

1. Ecrire une boucle qui affiche la table de multiplication par 7 pour les nombres de 1 à 10.​

```python
for i in range(1, 11):
    resultat = i * 7
    print(str(i) + " x 7 = " + str(resultat))
```

1. Ecrire une boucle qui affiche 100 fois « Je comprends l’algorithmie »​

```python
for i in range(100):
    print("Je comprends l'algorithmie")
```

1. Ecrire un algorithme qui demande un nombre de départ, et qui calcule la somme des entiers jusqu’à ce nombre. Par exemple, si l’on entre 5, le programme doit calculer: 1+2+3+4+5=15​

```python
total = 0
max = int(input("Saisissez un nombre"))

for i in range(0, max + 1):
    total = total + i

print("Le résultat est : "+str(total))
```

## Exercices

Dans cette série d'exercice, tous les concepts vues peuvent être utilisées (tests, boucles). Pour chaque exercice faire l'algorigramme et écrire le programme en python.

### Exercice 1

Un magasin de reprographie propose les tarifs suivants :​

* 0,15 cts si moins de 50 copies,​
* 0,10 cts au delà.​

Ecrire un programme qui affiche le prix en fonction du nombre de copie demandées.​

### Exercice 2

Ecrire un programme qui lance 100 fois une pièce. Calculer le nombre de fois où la pièce est pile et le nombre de fois ou elle est face​.

En python, on pourrait utiliser une fonction qui donne aléatoirement un nombre. Et considérer que s'il est pair alors c'est pile, et sinon c'est face.

```python
pileouface= random.randint(0, 1) //soit 0, soit 1
```

```python
import random

face = 0
pile = 0

... Compléter le code
```

### Exercice 3

Ecrire un programme qui demande deux valeurs (nombre 1 et nombre 2) et qui inverse les valeurs avant de les afficher.​

### Exercice 4

Ecrire un programme qui détermine le plus grand des deux nombres saisis.​
