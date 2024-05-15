# Correction puissance 4



{% code lineNumbers="true" %}
```python
import tkinter as tk

# Créer la fenêtre
fenetre = tk.Tk()
fenetre.title("Jeu de puissance 4")

# Création du canevas
canvas = tk.Canvas(fenetre, width=500, height=400, bg="white")
canvas.pack()

nbCols = 7
nbLignes = 6
rayon = 20

global cursor


def move_right(event):
  print("droite")
  canvas.move(cursor, 50, 0)


def move_left(event):
  print("gauche")
  canvas.move(cursor, -50, 0)


for col in range(nbCols):
  for ligne in range(nbLignes):
    posX = col * 50 + 25
    posY = ligne * 50 + 25
    rayonX = 20
    rayonY = 20

    canvas.create_oval(posX - rayon, posY - rayon, posX + rayon, posY + rayon)

cursor = canvas.create_rectangle(20, 300, 30, 310, fill="black")

fenetre.bind("<Right>", move_right)
fenetre.bind("<Left>", move_left)

# Lancer la boucle principale
fenetre.mainloop()

```
{% endcode %}
