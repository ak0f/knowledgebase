# Turtle

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Turtle #Grafik #random

---

## Was ist Turtle?

Grafik-Modul: Ich gebe Befehle an eine **Schildkröte**, die mit einem Stift auf eine **Leinwand** zeichnet. Gut zum Üben von Variablen, Schleifen und Funktionen.

![[turtle-beispiele.png]]

```python
from turtle import *

t = Turtle()
# ... Befehle ...
mainloop()        # hält das Fenster offen
```

---

## Bewegen

| Befehl | Wirkung |
|--------|---------|
| `forward(n)` | n Pixel vorwärts |
| `right(w)` / `left(w)` | um w Grad drehen |
| `goto(x, y)` | zu Koordinaten, `(0, 0)` = Mitte |
| `penup()` / `pendown()` | Stift heben / senken |
| `speed(0)` | maximale Geschwindigkeit |

**forward vs. goto:** `forward` ist relativ (hängt von Position und Blickrichtung ab), `goto` ist absolut (Richtung egal).

```python
t.forward(100)
t.penup()
t.goto(150, 0)      # ohne Linie
t.pendown()
t.forward(100)
```

---

## Zufall

```python
import random

for _ in range(100):
    t.forward(random.randint(50, 100))
    t.right(random.randint(0, 360))
```

`random.randint(a, b)` = zufällige ganze Zahl von a bis b.

---

## Formen

```python
for i in range(4):          # Quadrat
    t.forward(100)
    t.right(90)
```

```python
seitenanzahl = 6            # Vieleck
seitenlaenge = 100
winkel = 360 / seitenanzahl

for i in range(seitenanzahl):
    t.forward(seitenlaenge)
    t.left(winkel)
```

![[turtle-sechseck.png]]

Winkel pro Ecke = **360 / Anzahl Seiten**.

---

→ [[06 - For-Schleife]] · [[13 - Funktionsaufrufe]] · [[14 - Eigene Funktionen]]
