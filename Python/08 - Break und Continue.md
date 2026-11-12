# Break und Continue

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Schleifen #break #continue

---

| | `break` | `continue` |
|---|---------|-----------|
| Wirkung | beendet die **ganze Schleife** | überspringt nur den **aktuellen Durchlauf** |
| Danach | Code nach der Schleife | nächster Durchlauf |

---

## break

Wenn etwas gefunden wurde, das Ziel erreicht ist oder ein Fehler auftritt.

```python
while True:
    text = input("Eingabe (oder 'stop'): ")
    if text == "stop":
        break
    print(text)

for number in [3, 7, 2, 9, 5]:
    if number == 9:
        print("Treffer!")
        break
```

## continue

Wenn bestimmte Werte nicht bearbeitet werden sollen. Der Rest im Block wird übersprungen.

```python
for number in [3, -1, 5, 0, -7, 8]:
    if number <= 0:
        continue
    print(number)
```

---

## Bei while und for

- **while:** Bedingung selber verwalten, sonst Endlosschleife. `break` ist oft der Notausgang.
- **for:** Zähler läuft automatisch.
- Beide machen mehrere Ausgänge im Block (**Code Smell**). In kleinen Scripts ok, in grossen Projekten sparsam nutzen.

---

## Typische Fehler

```python
for n in range(5):
    print(n)
    break              # bricht nach dem 1. Durchlauf ab, Bedingung fehlt

for n in range(5):
    continue
    print(n)           # wird nie ausgeführt

while True:
    text = input()
    if text == "":
        continue       # kein Ausstieg → Endlosschleife

for i in range(3):
    for j in range(3):
        if j == 1:
            break      # beendet nur die innere Schleife
```

---

→ [[06 - For-Schleife]] · [[07 - While-Schleife]] · [[09 - Indents und Scopes]]
