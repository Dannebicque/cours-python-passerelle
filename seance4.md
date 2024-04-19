# Séance 4 : Un peu de graphique

## Introduction

Python dispose de nombreuses librairies permettant de faire un peu plus qu'un simple script dans une console.

Par exemple des interfaces graphiques (tkinter), des jeux (pygames), des graphiques (matplotlib), des calculs scientifiques (numpy), etc.

Nous allons ici découvrir la librairie tkinter, qui permet de créer des interfaces graphiques et des animations.

## Environnement de tests

Pour éviter de devoir installer tous les éléments sur les machines de l'unviersité, nous allons utiliser un environnement en ligne. 

Nous pouvons utiliser le site [repl.it](https://replit.com/), qui permet de créer des projets en ligne.

## Utilisation de tkinter

### Initialisation

Pour utiliser tkinter, il faut importer la librairie, et créer une fenêtre principale.

```python
from tkinter import *
```

Le documentation officielle se trouve ici : [https://tkdocs.com/tutorial/index.html](https://tkdocs.com/tutorial/index.html)

### Fenetre

Il faut ensuite créer une fenetre :

```python
fenetre = tk.Tk()
```

Il est possible de personnaliser la fenêtre, par exemple en lui donnant un titre :

```python
fenetre.title("Ma fenêtre")
```

L'affichage de la fenêtre se fait avec la fonction `mainloop` :

```python
fenetre.mainloop()
```

Le code minimale pour afficher une fenetre sera donc :

```python
import tkinter as tk

fenetre = tk.Tk()
fenetre.title("Ma fenêtre")
fenetre.mainloop()
```

### Zone de dessin

Une fenetre est ensuite une zone qui peut contenir des boutons, des textes, ... Il faut le préciser et les positionner.

Nous allons créer une zone "Canvas" (qui permet de dessiner) :

```python
largeur = 500
hauteur = 500

canvas = tk.Canvas(fenetre, width=largeur, height=hauteur, bg='white')
canvas.pack()
```

La fonction Canvas contient les paramètres suivants :

- fenetre : la fenêtre dans laquelle le canvas doit être affiché
- width : la largeur du canvas
- height : la hauteur du canvas
- bg : la couleur de fond du canvas

La syntaxe avec le `xxx=valeur` permet de préciser le nom des paramètres, ce qui permet de les mettre dans l'ordre que l'on veut.

`pack` permet de placer le canvas dans la fenêtre.

### Dessiner des formes

Il est possible de dessiner des formes sur le canvas :

```python
canvas.create_line(0, 0, 200, 100)
```

La fonction `create_line` permet de dessiner une ligne. Les paramètres sont les coordonnées des points de départ et d'arrivée.

Le point de départ se trouve toujours en haut à gauche de la fenêtre.

Toutes les options de create_line sont [ici](https://tkdocs.com/shipman/create_line.html).

Fair une ligne sur plusieurs lignes :

```python
canvas.create_line(0, 0, 200, 100, 300, 200, 400, 300)
```

Il est possible de dessiner d'autres formes, comme des rectangles :

```python
canvas.create_rectangle(50, 25, 150, 75, fill="blue")
```

La fonction `create_rectangle` permet de dessiner un rectangle. Les paramètres sont les coordonnées des points de départ et d'arrivée, et la couleur de remplissage.

Il est possible de dessiner des cercles :

```python
canvas.create_oval(10, 10, 100, 100, outline="red", width=2)
```

La fonction `create_oval` permet de dessiner un cercle. Les paramètres sont les coordonnées des points de départ et d'arrivée, la couleur de contour et la largeur du contour.

Il est possible de dessiner du texte :

```python
canvas.create_text(100, 100, text="Bonjour")
```

La fonction `create_text` permet de dessiner du texte. Les paramètres sont les coordonnées du point de départ et le texte à afficher.

### Déplacer des formes

Il est possible de déplacer des formes :

```python
canvas.move(objet, 5, 0)
```

La fonction `move` permet de déplacer un objet. Les paramètres sont l'objet à déplacer, et les coordonnées du déplacement.

On peut récupérer les coordonnées d'un objet :

```python
positions = canvas.coords(objet)
```

La fonction `coords` permet de récupérer les coordonnées d'un objet. Les paramètres sont l'objet à déplacer. Les coordonnées sont retournées sous forme d'une liste. Les éléments de la liste sont les coordonnées des points de départ et d'arrivée.

## Exercices

### Exercice 1

Créez une fenêtre avec un canvas de 500x500, et dessinez un rectangle bleu de 50x50 à 100x100.

### Exercice 2

Créez une fenêtre avec un canvas de 500x500, et dessinez un cercle rouge de 50x50 à 100x100.

## Notion de fonctions

Pour la suite nous allons avoir besoin de créer des fonctions. Une fonction est une suite d'instructions que l'on peut appeler plusieurs fois.

Une fonction se crée avec le mot clé `def` :

```python
def ma_fonction():
    print("Bonjour")
```

L'utilisation de cette fonction se fait de la manière suivante :

```python
ma_fonction()
```

Il est possible de passer des paramètres à une fonction :

```python
def ma_fonction(nom):
    print("Bonjour", nom)
```

L'utilisation de ses fonctions se fait de la manière suivante :

```python
ma_fonction("toto")
```

Il est possible de retourner une valeur :

```python
def ma_fonction(nom):
    return "Bonjour " + nom
```

L'utilisation de ses fonctions se fait de la manière suivante :

```python
message = ma_fonction("toto")
print(message)
```

Ce concept est très utilisé en programmation et permet d'éviter de recopier du code et d'avoir une approche modulaire.

### Exercice 1 sur les fonctions

Ecrire une fonction qui prend en paramètre un nombre, et qui **affiche** le carré de ce nombre.

Appeler cette fonction avec 3 nombres.

### Exercice 2 sur les fonctions

Ecrire une fonction qui prend en paramètre un nombre, et qui **retourne** la somme des nombres de 1 à ce nombre.

Appeler cette fonction avec 3 nombres et afficher les résultats.

## Animation

Une animation consiste à faire bouger des objets sur l'écran. Pour cela, il faut raffraichir l'écran régulièrement avec la fonction `update`.

### Exercice 3

Faire déplacer un carré ou une boule de la droite vers la gauche au milieu de l'écran.

Pour raffraichir l'écran, il faut utiliser la fonction `update` :

```python
canvas.update()
```

Pour executer une opération toutes les xx milisecondes :

```python
fenetre.after(100, fonction)
```

Il faut ensuite créer une fonction qui déplace l'objet, et qui appelle la fonction `after` pour se rappeler elle-même.

## Gestion des événements claviers

La librairie tkinter permet de gérer les événements claviers, c'est à dire détecter quand une touche est pressée et laquelle. Pour chaque touche il est ensuite possible de définir une action.

Pour récupérer une touche pressée, il faut utiliser la fonction `bind` :

```python
fenetre.bind("<Key>", fonction)
```

La fonction `bind` permet de lier un événement à une fonction. Les paramètres sont l'événement à lier, et la fonction à appeler.

`"<key>"` est l'événement qui correspond à une touche pressée. Par exemple `"<Left>"` correspond à la touche flèche gauche.

Vous trouverez la liste des événements [ici](https://tkinterexamples.com/events/keyboard/).

### Exercice 4

Faire déplacer un carré en utilisant les touches flèches droite et gauche.