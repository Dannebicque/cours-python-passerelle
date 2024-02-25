# Séance 4

L’ordinateur choisit un mot au hasard dans une liste, un mot de dix lettres maximum. Le joueur doit trouver les lettres composant le mot.

* À chaque coup, il saisit une lettre.
* Si la lettre figure dans le mot, l’ordinateur affiche le mot avec les lettres déjà trouvées.
* Celles qui ne le sont pas encore sont remplacées par des barres (\_).
* Le joueur a 6 chances. Au delà, il a perdu.

## Savoir si une lettre est dans un mot

En python, pour savoir si quelque chose est dans un tableau, on peut utiliser l'instruction `in`. Et par chance (et comme dans quasiment tous les langages de programmation), une chaîne de caractère (du texte), c'est un tableau !

Essayez le programme ci-dessous :

```python
mot = "Bonjour"
print(mot[2])
//affichera n (le troisième caractère, puisque le tableau commence à 0)
```

Maintenant essayez le code ci-dessous :

```python
mot = "Bonjour"

if "e" in mot:
    print("Le e est dans le mot")
else:
    print ("non, pas de e")
```

## Exercice

Modifiez le programme précédent pour que :

* Ce ne soit pas toujours la lettre "e" mais une lettre saisie par l'utilisateur
* Ce ne soit pas toujours le mot "Bonjour", mais un mot saisi par l'utilisateur

## Savoir où se trouve la lettre

Avec les exemples précédents, on sait maintenant que la lettre est dans le tableau, mais on ne sait pas où. Pour cela, en python, on peut utiliser `index`. Essayer le code ci-dessous.

```python
mot = "Bonjour"

print(mot.index("j"))

//doit afficher 3, qui est la position de "j" en partant de 0
```

## Exercice

Modifiez le code précédent, pour dire si la lettre est dans le mot, mais aussi sa position.

## Transformer une chaîne de caractères en liste

Même si une chaîne de caractères ressemble beaucoup à une liste (on peut accéder à un élément précis avec son indice), ce n'est pas une liste au sens de python, et on ne peut donc pas tout faire. Pour transformer une chaîne en liste, on peut utiliser l'instruction "`list`". Essayer le code ci-dessous :

```python
mot = "Bonjour"

listemot = list(mot)

print(", ".join(listemot))
```

## Effacer un élément d'une liste

L'instruction pop permet de retirer un élément d'une liste. Testez l'exemple ci-dessous :

```python
liste = ["a", "b","c", "d", "e","f"]

print(", ".join(liste))

liste.pop(2)

print(", ".join(liste))
```

## Ajouter un élément dans une liste

L'instruction insert permet d'ajouter un élément à une position définie.

```python
liste = ["a", "b","c", "d", "e","f"]

print(", ".join(liste))

liste.insert(2, "z")

print(", ".join(liste))
```

## Exercice

Ecrire un programme qui supprime la lettre saisie par l'utilisateur d'un mot. Que se passe-t-il si la lettre est présente plusieurs fois dans le mot ?

Ecrire un programme qui remplace une lettre par une autre. L'utilisateur indique la lettre à remplacer, et indique également la nouvelle lettre.

## On se lance...

Vous avez maintenant tous les éléments nécessaire pour essayer de faire fonctionner votre jeu du pendu...

Voici quelques étapes :

1. Choisir un mot parmi les mots disponible
2. Initialiser le nombre de vie, et le mot "vide" (c'est à dire avec aucune lettre de trouvée)
3. Demander à l'utilisateur de saisir une lettre
4. Regarder si la lettre est dans le mot
   1. Si oui, alors trouver sa position, et remplacer dans le mot "vide" par la lettre trouvée
   2. Si non, retirer une vie
   3. On recommence tant que l'utilisateur dispose de vies
