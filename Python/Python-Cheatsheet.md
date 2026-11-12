# Python Cheatsheet

**Tags:** #Python #Cheatsheet #Prüfung

---

## Ein- und Ausgabe

```python
print("Text", variable, sep=", ", end="")
name = input("Name: ")
age = int(input("Alter: "))
print(f"{name} ist {age} Jahre alt, Preis {price:.2f} CHF")
```

→ [[16 - Stdin und Stdout]]

---

## Datentypen und Casting

| Typ | Beispiel | Umwandlung |
|-----|----------|------------|
| `int` | `42` | `int("42")` |
| `float` | `3.14` | `float("3.14")` |
| `str` | `"Hallo"` | `str(42)` |
| `bool` | `True` / `False` | `bool("x")` |

`type(x)` zeigt den Typ. `input()` liefert immer `str`. → [[02 - Variablen und Datentypen]]

---

## Operatoren

| Art | Operatoren |
|-----|------------|
| Rechnen | `+ - * /` `//` (ganzzahlig) `%` (Rest) `**` (Potenz) |
| Vergleich | `== != > < >= <=` |
| Logik | `and` `or` `not` |
| Zuweisung | `=` `+=` `-=` `*=` |

→ [[03 - Mathematische Operatoren]], [[04 - Boolsche Operatoren]]

```python
round(3.14159, 2)    abs(-7)    min(1, 2)    max(1, 2)    sum([1, 2])
import math          math.sqrt(25)    math.pi    math.ceil(3.1)    math.floor(3.9)
```

---

## Entscheidungen

```python
if bedingung:
    ...
elif andere_bedingung:
    ...
else:
    ...
```

→ [[05 - Entscheidungen mit if, elif und else]]

---

## Schleifen

```python
for i in range(start, stop, step):    # stop nicht dabei
    ...
for item in liste:
    ...
while bedingung:
    ...
    break       # Schleife beenden
    continue    # nächster Durchlauf
```

→ [[06 - For-Schleife]], [[07 - While-Schleife]], [[08 - Break und Continue]]

---

## Strings

```python
s = "Python"
s[0]  s[-1]  len(s)  s[1:4]
s.lower()  s.upper()  s.strip()  s.replace("a", "b")
s.split(",")  ",".join(liste)  s.find("x")  s.count("a")
s.startswith("P")  s.isdigit()  s.isalpha()  "yt" in s
```

Escapes: `\n` neue Zeile, `\t` Tab, `\\` Backslash, `\"` Anführungszeichen

→ [[10 - Characters und Strings]], [[11 - Strings Extended]]

---

## Dateien

```python
with open("datei.txt", "w") as f:    # w = überschreiben, a = anhängen, r = lesen
    f.write("Text\n")
with open("datei.txt", "r") as f:
    for line in f:
        print(line, end="")
```

---

## Listen

```python
l = [1, 2, 3]
l.append(4)  l.insert(0, 9)  l.remove(2)  l.pop()  l.pop(0)  l.clear()
l.sort()  l.reverse()  l.copy()  l.index(3)
len(l)  l[0]  l[-1]  3 in l
```

## Dictionaries

```python
d = {"name": "Alice", "age": 17}
d["name"]  d.get("x", 0)  d["city"] = "Bern"  del d["age"]  d.pop("city")
for k, v in d.items():
    ...
```

→ [[12 - Listen und Dictionaries]]

---

## Funktionen

```python
def funktion(parameter, optional=1):
    return parameter * optional

ergebnis = funktion(5)
```

| Begriff | Bedeutung |
|---------|-----------|
| Parameter | Platzhalter in `def` |
| Argument | Wert beim Aufruf |
| `return` | gibt Wert zurück (≠ `print`) |

→ [[13 - Funktionsaufrufe]], [[14 - Eigene Funktionen]]

---

## Fehler

| Fehler | Ursache |
|--------|---------|
| `SyntaxError` | Klammer/Anführungszeichen/`:` fehlt |
| `IndentationError` | falsche Einrückung |
| `NameError` | Variable unbekannt |
| `TypeError` | Typen passen nicht (`"a" + 5`) |
| `ValueError` | `int("abc")` |
| `IndexError` | Index ausserhalb |
| `KeyError` | Schlüssel fehlt |
| `ZeroDivisionError` | Division durch 0 |

→ [[18 - Debugging]]

```python
assert funktion(3) == 6     # Unittest
```

→ [[19 - Entwickler-Tests]]

---

## PyCharm Shortcuts (Windows)

| Aktion | Shortcut |
|--------|----------|
| Ausführen | `Shift + F10` |
| Debuggen | `Shift + F9` |
| Breakpoint | `Strg + F8` |
| Step Over / Into / Resume | `F8` / `F7` / `F9` |
| Zeile kommentieren | `Strg + /` |
| Code formatieren | `Strg + Alt + L` |
| Überall suchen | `Doppel-Shift` |

→ [[01 - Python und IDE]]

---

## Turtle

```python
from turtle import *
t = Turtle()
t.forward(100)  t.right(90)  t.left(90)  t.goto(x, y)  t.penup()  t.pendown()  t.speed(0)
mainloop()
```

→ [[20 - Turtle]]
