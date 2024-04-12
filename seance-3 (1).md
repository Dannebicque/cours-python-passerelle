# Séance 3

## Le Juste prix

Le programme génère un prix rond aléatoire. Le but pour l’utilisateur est de deviner le prix. Chaque fois que l’utilisateur se trompe, l’ordinateur lui dit si c’est plus ou moins que le prix qu’il a donné. À chaque aide de l’ordinateur, le score final atteignable par le joueur baisse.

* Ecrire l'algorigramme du jeu
* Coder l'algorigramme en python

```python
import random

aleatoire = random.randint(min, max) 
//genere une valeur aléatoire entre min et max, entière

```

## Les listes

Dans cet exercice, nous allons avoir besoin d'une nouvelle forme de variable : les listes. Les listes sont très utilisés en programmation (on parle souvent aussi de tableaux), car elles permettent de sauvegarder plusieurs éléments dans une seule variable. Les listes peuvent être à une dimension (on va dire une colonne), à deux dimensions (un carré... comme Excel), ou à n dimension !

En python (et dans beaucoup de langage d'ailleurs), les tableaux s'écrivent de la manière suivante :

```python
montableau = ["element1", "element2", "element3", "...", "element n"]
```

Pour accéder à un élément d'une liste, on y va en indiquant sa position. Selon les langages la première valeur d'un tableau est à la position 0 ou à la position 1. **Très souvent, c'est la position 0, comme ici en python**.

```python
print(montableau[0]) //affichera element1
print(montableau[2]) //affichera element3
```

Il est possible de connaître la taille d'une liste :

<pre class="language-python"><code class="lang-python"><strong>len(montableau) //donne la taille du tableau/liste montableau
</strong></code></pre>

### Exercice

Soit la liste suivante

```python
formations = ["MMI", "TC", "GEA", "CJ", "GEII", "GMP"]
```

Ecrire un algorigramme qui affiche l'ensemble des valeurs du tableau. Le coder en python.

### Manipuler les listes

Il est également assez facile en python de créer une liste avec n fois un caractère. Essayez le code suivant :

```python
liste = "a" * 8

print(liste)
```

Grâce à l'instruction "join" on peut même formatter rapidement une liste, en insérant par exemple un caractère entre chaque élément de la liste. Essayez le code suivant :

```python
liste = "a" * 8
print(liste)

resultat = ', '.join(liste)
print(resultat)

```

### Exercice

Ecrire un programme qui génère une liste de "\_" en fonction de la taille d'un mot. La taille d'un mot se trouve avec l'instruction len (exemple : `taille = len(monmot)`).

Exemple, si le mot est "chat", je veux avoir à l'écran `_ _ _ _`

### Ajouter des éléments dans une liste

Pour ajouter un élément dans une liste python, on peut utiliser la fonction `append`, qui va ajouter un élément en fin de liste



```python
liste = [1, 2, 3, 4, 5]
liste.append(6)

//donner une liste avec les valeurs 1, 2, 3, 4, 5, 6
```

### Exercice

Demander à l'utilisateur de saisir 5 valeurs, les ajouter dans une liste et afficher cette liste.

### Exercice

Demander à l'utilisateur de saisir 5 valeurs, les ajouter dans une liste et afficher cette liste. Inverser les éléments de cette liste et afficher le résultat.
