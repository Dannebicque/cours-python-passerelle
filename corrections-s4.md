# Corrections S4

### **Séance 1 – Corrections**

#### 🔹 Tracer un carré

```python
pythonCopierModifierimport turtle

t = turtle.Turtle()

for i in range(4):
    t.forward(100)
    t.left(90)
```

***

#### 🔹 Maison (carré + toit)

```python
import turtle

t = turtle.Turtle()

# carré
for i in range(4):
    t.forward(100)
    t.left(90)

# triangle (toit)
t.left(90)
t.forward(100) 
t.right(90)

t.left(45)
t.forward(70)      # hypoténuse
t.right(90)
t.forward(70)
```

***

#### 🔹 Initiales simples (ex. : "AB")

```python
import turtle

t = turtle.Turtle()

# Lettre A
t.penup()
t.goto(-100, 0)
t.pendown()
t.setheading(90)
t.forward(50)
t.right(90)
t.forward(20)
t.right(90)
t.forward(25)
t.right(90)
t.forward(20)

# Lettre B
t.penup()
t.goto(0, 0)
t.setheading(90)
t.pendown()
t.forward(50)
t.right(90)
t.circle(-10, 180)  # boucle haute
t.right(180)
t.circle(-10, 180)  # boucle basse
```

***

### ✅ **Séance 2 – Corrections**

#### 🔹 Polygone régulier à `n` côtés

```python
import turtle

t = turtle.Turtle()

n = int(input("Combien de côtés ? "))
angle = 360 / n

for i in range(n):
    t.forward(100)
    t.left(angle)
```

***

#### 🔹 Rosace avec triangles

```python
import turtle

t = turtle.Turtle()

for i in range(36):
    for j in range(3):
        t.forward(50)
        t.left(120)
    t.left(10)
```

***

### ✅ **Séance 3 – Fonctions**

#### 🔹 Fonction étoile

```python
import turtle

t = turtle.Turtle()

def etoile(taille, couleur):
    t.color(couleur)
    for i in range(5):
        t.forward(taille)
        t.right(144)

etoile(100, "blue")
```

***

#### 🔹 Plusieurs étoiles alignées

```python
pythonCopierModifierfor i in range(5):
    t.penup()
    t.goto(i * 100 - 200, 0)
    t.pendown()
    etoile(50, "red")
```

***

### ✅ **Séance 4 – Aléatoire et feu d’artifice**

#### 🔹 Feu d’artifice

```python
import turtle
import random

t = turtle.Turtle()
colors = ["red", "blue", "green", "yellow", "purple"]

for i in range(10):
    t.penup()
    x = random.randint(-200, 200)
    y = random.randint(-200, 200)
    t.goto(x, y)
    t.pendown()
    t.color(random.choice(colors))
    for j in range(36):
        t.forward(50)
        t.left(170)
```

***

#### 🔹 Pluie de carrés

```python
import turtle
import random

t = turtle.Turtle()
colors = ["red", "blue", "green", "orange", "pink"]

for i in range(30):
    t.penup()
    t.goto(random.randint(-300, 300), random.randint(-300, 300))
    t.pendown()
    t.color(random.choice(colors))
    for j in range(4):
        t.forward(20)
        t.right(90)
```
