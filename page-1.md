# Page 1

```python
import random

listeDeMots = ['chat', 'chien', 'bonjour', 'université', 'bonjour', '...']
numero = random.randint(0, len(listeDeMots))

mot = listeDeMots[numero]

tailleDuMot = len(mot)
aDeviner = "_" * tailleDuMot
print(" ".join(aDeviner))
```
