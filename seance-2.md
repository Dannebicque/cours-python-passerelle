# Séance 2

## Le Juste prix

Le programme génère un prix rond aléatoire. Le but pour l’utilisateur est de deviner le prix. Chaque fois que l’utilisateur se trompe, l’ordinateur lui dit si c’est plus ou moins que le prix qu’il a donné. À chaque aide de l’ordinateur, le score final atteignable par le joueur baisse.

* Ecrire l'algorigramme du jeu
* Coder l'algorigramme en python

```python
import random

aleatoire = random.randint(min, max) 
//genere une valeur aléatoire entre min et max, entière

```

### Correction

```python
import random

nombre = random.randint(1,100)
trouve = False
pointDeVie = 10

while trouve == False and pointDeVie > 0:
    valeur = int(input("Saisir une valeur : "))
    if valeur == nombre:
        trouve = True
        print("Vous avez trouvé ! Score : " + str(pointDeVie))
    else:
        if valeur < nombre:
            pointDeVie = pointDeVie - 1
            print("C'est plus !")
        else:
            pointDeVie = pointDeVie - 1
            print("C'est moins !")

if pointDeVie == 0:
    print("Vous avez perdu ")
```

## Le jeu du pendu

L’ordinateur choisit un mot au hasard dans une liste, un mot de dix lettres maximum. Le joueur doit trouver les lettres composant le mot.

* À chaque coup, il saisit une lettre.
* Si la lettre figure dans le mot, l’ordinateur affiche le mot avec les lettres déjà trouvées.&#x20;
* Celles qui ne le sont pas encore sont remplacées par des barres (\_).
* Le joueur a 6 chances. Au delà, il a perdu.

### Les listes

Dans cet exercice, nous allons avoir besoin d'une nouvelle forme de variable : les listes. Les listes sont très utilisés en programmation (on parle souvent aussi de tableaux), car elles permettent de sauvegarder plusieurs éléments dans une seule variable. Les listes peuvent être à une dimension (on va dire une colonne), à deux dimensions (un carré... comme Excel), ou à n dimension !

En python (et dans beaucoup de langage d'ailleurs), les tableaux s'écrivent de la manière suivante :&#x20;

```python
montableau = ["element1", "element2", "element3", "...", "element n"]
```

Pour accéder à un élément d'une liste, on y va en indiquant sa position. Selon les langages la première valeur d'un tableau est à la position 0 ou à la position 1. **Très souvent, c'est la position 0, comme ici en python**.

```python
print(montableau[0]) //affichera element1
print(montableau[2]) //affichera element2
```

Il est possible de connaître la taille d'une liste : &#x20;

```python
montableau.size() //donne la taille du tableau/liste montableau
```

#### Exercice

Soit la liste suivante

```python
formations = ["MMI", "TC", "GEA", "CJ", "GEII", "GMP"]
```

Ecrire un algorigramme qui affiche l'ensemble des valeurs du tableau. Le coder en python.

### Manipuler les listes

Il est également assez facile en python de créer une liste avec n fois un caractère. Essayez le code suivant :&#x20;

```python
liste = "a" * 8

print(liste)
```

Grâce à l'instruction "join" on peut même formatter rapidement une liste, en insérant par exemple un caractère entre chaque élément de la liste. Essayez le code suivant :&#x20;

```python
liste = "a" * 8
print(liste)

resultat = ', '.join(liste)
print(resultat)

```

#### Exercice

Ecrire un programme qui génère une liste de "\_" en fonction de la taille d'un mot. La taille d'un mot se trouve avec l'instruction len (exemple : `taille = len(monmot)`).

Exemple, si le mot est "chat", je veux avoir à l'écran `_ _ _ _`

### Savoir si une lettre est dans un mot

En python, pour savoir si quelque chose est dans un tableau, on peut utiliser l'instruction `in`. Et par chance (et comme dans quasiment tous les langages de programmation), une chaîne de caractère (du texte), c'est un tableau !

Essayez le programme ci-dessous :&#x20;

```python
mot = "Bonjour"
print(mot[2])
//affichera n (le troisième caractère, puisque le tableau commence à 0)
```

Maintenant essayez le code ci-dessous :&#x20;

```python
mot = "Bonjour"

if "e" in mot:
    print("Le e est dans le mot")
else:
    print ("non, pas de e")
```

#### Exercice

Modifiez le programme précédent pour que :&#x20;

* Ce ne soit pas toujours la lettre "e" mais une lettre saisie par l'utilisateur
* Ce ne soit pas toujours le mot "Bonjour", mais un mot saisi par l'utilisateur

### Savoir où se trouve la lettre

Avec les exemples précédents, on sait maintenant que la lettre est dans le tableau, mais on ne sait pas où. Pour cela, en python, on peut utiliser `index`. Essayer le code ci-dessous.

```python
mot = "Bonjour"

print(mot.index("j"))

//doit afficher 3, qui est la position de "j" en partant de 0
```

#### Exercice

Modifiez le code précédent, pour dire si la lettre est dans le mot, mais aussi sa position.

### Transformer une chaîne de caractères en liste

Même si une chaîne de caractères ressemble beaucoup à une liste (on peut accéder à un élément précis avec son indice), ce n'est pas une liste au sens de python, et on ne peut donc pas tout faire. Pour transformer une chaîne en liste, on peut utiliser l'instruction "`list`". Essayer le code ci-dessous :&#x20;

```python
mot = "Bonjour"

listemot = list(mot)

print(", ".join(listemot))
```

### Effacer un élément d'une liste

L'instruction pop permet de retirer un élément d'une liste. Testez l'exemple ci-dessous :&#x20;

```python
liste = ["a", "b","c", "d", "e","f"]

print(", ".join(liste))

liste.pop(2)

print(", ".join(liste))
```

### Ajouter un élément dans une liste

L'instruction insert permet d'ajouter un élément à une position définie.

```python
liste = ["a", "b","c", "d", "e","f"]

print(", ".join(liste))

liste.insert(2, "z")

print(", ".join(liste))
```

#### Exercice

Ecrire un programme qui supprime la lettre saisie par l'utilisateur d'un mot. Que se passe-t-il si la lettre est présente plusieurs fois dans le mot ?

Ecrire un programme qui remplace une lettre par une autre. L'utilisateur indique la lettre à remplacer, et indique également la nouvelle lettre.

### On se lance...

Vous avez maintenant tous les éléments nécessaire pour essayer de faire fonctionner votre jeu du pendu...

Voici quelques étapes :&#x20;

1. Choisir un mot parmi les mots disponible
2. Initialiser le nombre de vie, et le mot "vide" (c'est à dire avec aucune lettre de trouvée)
3. Demander à l'utilisateur de saisir une lettre
4. Regarder si la lettre est dans le mot
   1. Si oui, alors trouver sa position, et remplacer dans le mot "vide" par la lettre trouvée
   2. Si non, retirer une vie
   3. On recommence tant que l'utilisateur dispose de vies
