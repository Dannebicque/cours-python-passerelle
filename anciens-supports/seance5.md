# Séance 5

## Etapes

### Dessin du plateau

Nous allons commencer par dessiner le plateau de jeu. Le plateau se compose de 6 lignes et 7 colonnes. Nous allons donc dessiner un rond pour chaque case, avec une bordure hachurée (pour les cases vides).

### Choix de la colonne

Pour faciliter le choix d'une colonne, nous allons leur donner une lettre (de A à G). L'appui sur une touche du clavier permettra de choisir la colonne.

L'appui sur la touche `A` permettra de choisir la colonne 1, l'appui sur la touche `B` permettra de choisir la colonne 2, etc. Le choix de la colonne fera tomber un jeton dans la colonne choisie. On alternera les couleurs des jetons.

### Chute du jeton

Lorsqu'un joueur choisit une colonne, le jeton doit tomber dans la colonne choisie, et se placer dans la première case vide de la colonne. La difficulté est donc de trouver la première case vide de la colonne choisie.

Pour cela, nous allons utiliser une liste pour chaque colonne. Chaque élément de la liste correspondra à une case. Si la case est vide, l'élément de la liste sera 0. Si la case est occupée, l'élément de la liste sera la couleur du jeton.

### Détection de la victoire

Nous allons détecter la victoire d'un joueur. Pour cela, nous allons vérifier si 4 jetons de la même couleur sont alignés horizontalement, verticalement ou en diagonale.

### Fin de partie

Nous allons détecter la fin de la partie. La partie se termine lorsqu'un joueur a gagné, ou lorsque le plateau est plein.
