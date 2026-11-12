# For-Schleife

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #for #Schleife #range

> Thema war nicht als PDF vorhanden, selbst zusammengefasst.

---

## Idee

Die `for`-Schleife nutzt man, wenn die Anzahl **bekannt** ist oder man **jedes Element** bearbeiten will. Der Zähler läuft automatisch.

```python
for i in range(5):
    print("Hallo")     # 5x
```

---

## range()

| Aufruf | Werte |
|--------|-------|
| `range(5)` | 0, 1, 2, 3, 4 |
| `range(2, 6)` | 2, 3, 4, 5 |
| `range(0, 10, 2)` | 0, 2, 4, 6, 8 |
| `range(10, 0, -1)` | 10, 9, ..., 1 |

`range(start, stop, step)`: `start` ist dabei, `stop` **nicht**. Standard: start 0, step 1.

---

## Über Sammlungen

```python
for fruit in ["Apfel", "Banane"]:      # Liste
    print(fruit)

for char in "Python":                  # String
    print(char)

for key, value in person.items():      # Dictionary
    print(key, value)

for i, fruit in enumerate(fruits):     # mit Index
    print(i, fruit)
```

---

## Typische Muster

```python
total = 0
for n in [5, 8, 2]:
    total += n                 # Summe

evens = []
for n in range(10):
    if n % 2 == 0:
        evens.append(n)        # Filtern
```

**Verschachtelt:** Die innere Schleife läuft bei jedem Durchlauf der äusseren komplett durch.

```python
for row in range(1, 4):
    for col in range(1, 4):
        print(row * col, end=" ")
    print()
```

`break` beendet die Schleife, `continue` überspringt einen Durchlauf. `for _ in range(3)`: Zähler wird nicht gebraucht.

---

## for vs. while

| | for | while |
|---|-----|-------|
| Wann | Anzahl bekannt / jedes Element | Anzahl unbekannt |
| Zähler | automatisch | selber |
| Endlosschleife | kaum | möglich |

**Fehler:** `range(5)` hat keine 5. `for i in liste` gibt Elemente, nicht Indizes.

---

→ [[05 - Entscheidungen mit if, elif und else]] · [[07 - While-Schleife]] · [[08 - Break und Continue]] · [[15 - Eigene range-Funktionen]]
