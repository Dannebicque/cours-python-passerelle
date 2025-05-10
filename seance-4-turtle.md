# Séance 4 : Turtle

## Présentation de Trinket

* En ligne, gratuit, pas d'installation
* Compatible Python + Turtle : [https://trinket.io](https://trinket.io)
* Sauvegarde, partage de lien, exécution directe

Une **fonction** permet de regrouper des instructions qu’on peut **réutiliser**.

## **Les fonctions en python**

### **Définir une fonction :**

```python
pythonCopierModifierdef bonjour():
    print("Bonjour à tous !")
```

### **Appeler une fonction :**

```python
pythonCopierModifierbonjour()  # Affiche : Bonjour à tous !
```

### **Fonction avec paramètres :**

```python
pythonCopierModifierdef dire_bonjour(prenom):
    print(f"Bonjour {prenom} !")

dire_bonjour("Alice")
```

### **Fonction qui retourne une valeur :**

```python
pythonCopierModifierdef addition(a, b):
    return a + b

resultat = addition(3, 4)  # 7
```

## **Introduction à `turtle`**

[**`https://docs.python.org/3/library/turtle.html`**](https://docs.python.org/3/library/turtle.html)

```python
pythonCopierModifierimport turtle  # Importe la bibliothèque turtle

t = turtle.Turtle()  # Crée une tortue
t.forward(100)       # Avance de 100 pixels
t.left(90)           # Tourne à gauche de 90 degrés
```

### **Commandes essentielles :**

* `forward(x)` : avancer de x pixels
* `left(angle)` / `right(angle)` : tourner
* `penup()` / `pendown()` : lever / baisser le crayon
* `goto(x, y)` : aller à une position précise
* `color("red")` : changer la couleur
* `speed(0)` : vitesse maximale

***

### **Exercices**

**1. Tracer un carré**

> Utilisez `forward()` et `left()` dans une boucle pour tracer un carré.

**2. Dessiner une maison**

> Un carré pour la base et un triangle pour le toit.

**3. Écrire ses initiales**

> Utilisez `penup()`, `pendown()` et `goto()` pour positionner la tortue et dessiner vos initiales.

## Boucles et dessins

### Objectifs :

* Répéter des instructions avec `for`
* Tracer des polygones réguliers (triangle, pentagone, hexagone…)
* Créer des motifs circulaires

### Exemple : polygone régulier

```python
pythonCopierModifier# Un carré
for _ in range(4):
    t.forward(100)
    t.left(90)
```

### Astuce :

Un polygone à `n` côtés a un angle de rotation de `360 / n`.

***

### Exercices :

1. **Tracer un polygone à `n` côtés** (saisie utilisateur)
2. **Créer une rosace** : dessiner plusieurs fois un triangle ou carré en tournant
3. **Défi mandala** : faire une forme complexe avec des boucles imbriquées

## **Fonctions et réutilisabilité**

### Objectifs :

* Organiser le code avec des fonctions
* Ajouter des paramètres (taille, couleur…)

### Exemple :

```python
pythonCopierModifierdef carre(taille):
    for _ in range(4):
        t.forward(taille)
        t.left(90)

carre(50)
carre(100)
```

### Fonction avec paramètres :

```python
pythonCopierModifierdef etoile(taille, couleur):
    t.color(couleur)
    for _ in range(5):
        t.forward(taille)
        t.right(144)
```

***

### Exercices :

1. **Créer une fonction étoile personnalisée**
2. **Composer une scène** : plusieurs étoiles, lune, maison…

***

## **Couleurs et hasard**

### Objectifs :

* Utiliser `random` pour placer et colorier des formes
* Créer des motifs aléatoires

### Importer `random`

```python
import random

couleurs = ['red', 'green', 'blue', 'yellow']
couleur_aleatoire = random.choice(couleurs)
x = random.randint(-200, 200)
y = random.randint(-200, 200)
```

***

### Exercices :

1. **Feu d’artifice** : plusieurs lignes en étoile, couleurs et positions aléatoires
2. **Pluie de carrés** : petits carrés colorés partout sur l’écran

***

## **Interaction clavier (jeu simple)**

### Objectifs :

* Réagir aux touches du clavier
* Faire bouger une tortue (comme dans un mini-jeu)

### Événements clavier :

```python
pythonCopierModifierdef up():
    t.setheading(90)
    t.forward(10)

screen = turtle.Screen()
screen.listen()
screen.onkey(up, "Up")  # quand on appuie sur flèche haut
```

***

### Exercices :

1. **Labyrinthe simple** : bouger la tortue pour l’amener à la sortie
2. **Attraper les étoiles** : déplacer une tortue pour rejoindre un point aléatoire
