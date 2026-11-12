# Break und Continue

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Schleifen #break #continue

---

## Lernziele

- [ ] `break` und `continue` erklären und unterscheiden
- [ ] Beide in `while`- und `for`-Schleifen anwenden
- [ ] Typische Fehler erkennen

---

## Überblick

| | `break` | `continue` |
|---|---------|-----------|
| Wirkung | beendet die **ganze Schleife** sofort | beendet nur den **aktuellen Durchlauf** |
| Danach | Code nach der Schleife | nächster Durchlauf |
| Code danach im Block | wird nicht mehr ausgeführt | wird übersprungen |

---

## break

Wofür? Eingabe erkannt, Ziel erreicht (Zahl gefunden), Fehlerfall.

```python
# Endlosschleife mit Ausstieg
while True:
    text = input("Gib etwas ein (oder 'stop'): ")
    if text == "stop":
        break
    print(f"Du hast '{text}' eingegeben.")
```

```python
# Suche abbrechen
numbers = [3, 7, 2, 9, 5]
for number in numbers:
    print(f"Prüfe {number}")
    if number == 9:
        print("Treffer! Abbruch.")
        break
```

---

## continue

Wofür? Ungültige Eingaben ignorieren, bestimmte Werte nicht bearbeiten.

```python
numbers = [3, -1, 5, 0, -7, 8]
for number in numbers:
    if number <= 0:
        continue
    print(f"Positive Zahl: {number}")
```

```python
# Ungültige Eingabe überspringen
while True:
    number = input("Gib eine Zahl ein (oder 'x'): ")
    if number == "x":
        break
    if not number.isdigit():
        print("Keine gültige Zahl.")
        continue
    print(f"Doppelt: {int(number) * 2}")
```

---

## Mit while vs. for

- **while:** Bedingung selber verwalten, sonst Endlosschleife. `break` als "Notausgang".
- **for:** Zähler wird automatisch verwaltet.

> **Achtung (Code Smell):** `break` und `continue` schaffen mehrere Ausgänge in einem Schleifenblock. Das macht Code schwerer lesbar und testbar. In kleinen Scripts ok, in grossen Projekten sparsam einsetzen.

---

## Typische Fehler

**1. break ohne Bedingung**

```python
for number in range(5):
    print(number)
    break          # Schleife stoppt nach dem 1. Durchlauf
```

Besser: `if number == 3: break`

**2. continue vor dem restlichen Code**

```python
for number in range(5):
    continue
    print(number)  # wird nie ausgeführt
```

**3. Endlosschleife mit continue**

```python
while True:
    text = input("Text: ")
    if text == "":
        continue   # nie ein Ausstieg
```

**4. break in verschachtelten Schleifen**

```python
for i in range(3):
    for j in range(3):
        if j == 1:
            break   # beendet nur die innere Schleife
    print(i)
```

---

## Verknüpfungen

→ [[06 - For-Schleife]]
→ [[07 - While-Schleife]]
→ [[09 - Indents und Scopes]]
