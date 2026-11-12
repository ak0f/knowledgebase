# For-Schleife

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #for #Schleife #range #Iteration

> Dieses Thema hattest du nicht als PDF. Die Notiz ist selbst verfasst, im gleichen Stil wie die anderen.

---

## Lernziele

- [ ] Eine `for`-Schleife schreiben
- [ ] `range()` mit start, stop und step nutzen
- [ ] Über Listen, Strings und Dictionaries iterieren
- [ ] Schleifen verschachteln

---

## Idee

Eine **Schleife** wiederholt Code. Die `for`-Schleife nutzt man, wenn die **Anzahl Wiederholungen bekannt** ist oder man **jedes Element** einer Sammlung bearbeiten will.

```python
for i in range(5):
    print("Hallo")     # 5x
```

- Variable (`i`) bekommt bei jedem Durchlauf den nächsten Wert
- Der Schleifenzähler wird **automatisch** verwaltet
- Der Block ist wie bei `if` **eingerückt** und nach `:`
- Ein Durchlauf heisst **Iteration**

---

## range()

| Aufruf | Werte |
|--------|-------|
| `range(5)` | 0, 1, 2, 3, 4 |
| `range(2, 6)` | 2, 3, 4, 5 |
| `range(0, 10, 2)` | 0, 2, 4, 6, 8 |
| `range(10, 0, -1)` | 10, 9, 8, ..., 1 |

- `range(start, stop, step)`
- `start` ist **dabei**, `stop` ist **nicht dabei**
- Standard: `start=0`, `step=1`

```python
for i in range(1, 4):
    print(i)       # 1 2 3
```

Eigene Version: [[15 - Eigene range-Funktionen]]

---

## Über Sammlungen iterieren

### Liste

```python
fruits = ["Apfel", "Banane", "Kirsche"]
for fruit in fruits:
    print(fruit)
```

### String

```python
for char in "Python":
    print(char)
```

### Dictionary

```python
person = {"name": "Alice", "age": 17}

for key in person:
    print(key, person[key])

for key, value in person.items():
    print(f"{key}: {value}")
```

### Mit Index

```python
for i in range(len(fruits)):
    print(i, fruits[i])

for i, fruit in enumerate(fruits):     # eleganter
    print(i, fruit)
```

---

## Typische Muster

**Summe berechnen**

```python
total = 0
for number in [5, 8, 2]:
    total += number
print(total)    # 15
```

**Zählen**

```python
count = 0
for char in "Banane":
    if char == "a":
        count += 1
```

**Filtern in neue Liste**

```python
evens = []
for n in range(10):
    if n % 2 == 0:
        evens.append(n)
```

**Mit Turtle zeichnen**

```python
for i in range(4):
    t.forward(100)
    t.right(90)
```

---

## Verschachtelte Schleifen

```python
for row in range(1, 4):
    for col in range(1, 4):
        print(row * col, end=" ")
    print()
```

```
1 2 3
2 4 6
3 6 9
```

Die **innere** Schleife läuft bei jedem Durchlauf der äusseren komplett durch.

---

## break, continue und `_`

```python
for number in [3, 7, 9, 5]:
    if number == 9:
        break          # Schleife beenden
    if number < 4:
        continue       # diesen Durchlauf überspringen
    print(number)

for _ in range(3):     # _ = Zähler wird nicht gebraucht
    print("Hi")
```

Mehr dazu: [[08 - Break und Continue]]

---

## for vs. while

| | `for` | `while` |
|---|-------|---------|
| Einsatz | bekannte Anzahl / jedes Element | unbekannte Anzahl, bis Bedingung erfüllt |
| Zähler | automatisch | selbst verwalten |
| Endlosschleife | kaum möglich | möglich |

---

## Typische Fehler

- `range(5)` enthält die **5 nicht** (bis 4)
- Liste **während** der Schleife verändern (Elemente überspringen)
- Einrückung vergessen
- `i` mit dem Element verwechseln: `for i in fruits` gibt Elemente, nicht Indizes

---

## Übungen

1. Zahlen von 1 bis 10 ausgeben
2. Kleines Einmaleins einer eingegebenen Zahl
3. Summe aller Zahlen von 1 bis 100
4. Vokale in einem Wort zählen
5. Dreieck aus Sternen:

```python
for i in range(1, 6):
    print("*" * i)
```

---

## Verknüpfungen

→ [[05 - Entscheidungen mit if, elif und else]]
→ [[07 - While-Schleife]]
→ [[12 - Listen und Dictionaries]]
→ [[20 - Turtle]]
