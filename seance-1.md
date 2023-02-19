# Séance 1

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

```python
nbcopies = int(input("Nombre de copies désiré ? "))

if nbcopies < 50:
    tarif = nbcopies * 0.15
else:
    tarif = nbcopies * 0.10

print("total à payer : " + str(tarif) + " €")
```

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

for i in range(100):
    pileouface = random.randint(0, 1)
    print(str(pileouface))
    if pileouface == 0:
        pile = pile + 1
    else:
        face = face + 1

print("Nombre de tirage pile : "+str(pile)+", nombre de tirage face :" + str(face))y
```

### Exercice 3

Ecrire un programme qui demande deux valeurs (nombre 1 et nombre 2) et qui inverse les valeurs avant de les afficher.​

### Exercice 4

Ecrire un programme qui détermine le plus grand des deux nombres saisis.​
