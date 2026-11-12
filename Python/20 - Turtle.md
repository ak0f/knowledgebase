# Turtle

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Turtle #Grafik #Schleifen #random

---

## Lernziele

- [ ] Die Turtle-Bibliothek importieren
- [ ] Turtle relativ (`forward`, `left`, `right`) und absolut (`goto`) bewegen
- [ ] Stift heben und senken
- [ ] Mit Zufall (`random`) zeichnen
- [ ] Variablen, Schleifen und Funktionen für Formen nutzen

---

## Was ist Turtle?

Grafisches Modul in Python: Befehle an eine virtuelle **Schildkröte**, die mit einem Stift auf einer **Leinwand** (Fenster) zeichnet. Gut zum Üben von Variablen, Schleifen und Funktionsaufrufen.

![[turtle-beispiele.png]]

---

## Importieren und Grundgerüst

```python
from turtle import *

t = Turtle()
# ... Befehle ...
mainloop()   # hält das Fenster offen
```

---

## Bewegen

### Relativ (zur aktuellen Position und Richtung)

| Befehl | Wirkung |
|--------|---------|
| `forward(distance)` | vorwärts in Blickrichtung (Pixel) |
| `right(angle)` | um Winkel nach rechts drehen |
| `left(angle)` | um Winkel nach links drehen |

```python
t.forward(100)
t.right(90)
t.forward(100)
```

### Absolut mit goto(x, y)

`(0, 0)` ist das **Zentrum** der Leinwand. Die Ausrichtung spielt keine Rolle.

```python
t.goto(100, 100)
t.goto(-100, -100)
```

### goto() vs. forward()

| | `forward()` | `goto()` |
|---|-------------|----------|
| Bewegung | relativ zu Position und Ausrichtung | absolut zu Koordinaten |
| Richtung | hängt davon ab, wohin die Turtle schaut | egal |

---

## Stift heben und senken

| Befehl | Wirkung |
|--------|---------|
| `penup()` | Stift heben, Bewegung ohne Linie |
| `pendown()` | Stift senken, Bewegung zeichnet wieder |

```python
t.forward(100)
t.penup()
t.goto(150, 0)
t.pendown()
t.forward(100)
```

---

## Zufall mit random

```python
from turtle import *
import random

t = Turtle()
t.speed(0)   # maximale Geschwindigkeit

for _ in range(100):
    t.forward(random.randint(50, 100))
    t.right(random.randint(0, 360))

mainloop()
```

- `random.randint(a, b)` = zufällige ganze Zahl von a bis b (inklusive)
- Ergebnis: chaotische, unvorhersehbare Zeichnung

---

## Beispiele

### Quadrat

```python
from turtle import *
t = Turtle()
for i in range(4):
    t.forward(100)
    t.right(90)
mainloop()
```

### Regelmässiges Vieleck mit Variablen

```python
from turtle import *

t = Turtle()
t.speed(5)

seitenanzahl = 6        # 6 = Sechseck
seitenlaenge = 100
winkel = 360 / seitenanzahl

for i in range(seitenanzahl):
    t.forward(seitenlaenge)
    t.left(winkel)

mainloop()
```

![[turtle-sechseck.png]]

> Winkel pro Ecke = **360 / Anzahl Seiten**.

### Übungen

- Quadrat mit `goto(x, y)` zeichnen
- Zwei parallele Dreiecke mit `penup()` / `pendown()`
- Vieleck als **Funktion** mit Parametern `seiten` und `laenge`

---

## Verknüpfungen

→ [[06 - For-Schleife]]
→ [[13 - Funktionsaufrufe]]
→ [[14 - Eigene Funktionen]]
