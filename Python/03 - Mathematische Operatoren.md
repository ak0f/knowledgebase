# Mathematische Operatoren

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Mathe #math #Runden

---

## Operatoren

| Operator | Bedeutung | Beispiel |
|----------|-----------|----------|
| `+ - *` | Plus, Minus, Mal | `6 * 2` → 12 |
| `/` | Division (immer `float`) | `8 / 2` → 4.0 |
| `//` | ganzzahlige Division | `7 // 2` → 3 |
| `%` | Modulo (Rest) | `7 % 2` → 1 |
| `**` | Potenz | `2 ** 3` → 8 |

Punkt vor Strich, Klammern zuerst. Kommazahlen mit **Punkt** schreiben (`19.95`).

```python
minutes = 125
print(minutes // 60, minutes % 60)   # 2 Stunden, 5 Minuten
```

Modulo brauche ich z. B. für gerade/ungerade (`x % 2 == 0`) oder "jeden 5. Schritt".

---

## Mit Eingaben rechnen

`input()` gibt einen String → mit `int()` oder `float()` umwandeln.

```python
length = float(input("Länge: "))
width = float(input("Breite: "))
print(f"Fläche: {length * width} m2")
```

Wenn die Eingabe keine Zahl ist, gibt es einen Fehler (später mit `try/except` abfangen).

---

## Runden und formatieren

```python
round(3.14159)       # 3
round(3.14159, 2)    # 3.14
print(f"{19.9999:.2f} CHF")   # 20.00 CHF
```

`:.2f` = 2 Nachkommastellen.

---

## Eingebaute Funktionen

| Funktion | Bedeutung |
|----------|-----------|
| `abs(x)` | Betrag |
| `pow(x, y)` | Potenz |
| `min(...)` / `max(...)` | kleinster / grösster Wert |
| `sum(liste)` | Summe |
| `round(x, n)` | runden |

---

## Bibliothek math

```python
import math
```

| Funktion | Bedeutung |
|----------|-----------|
| `math.sqrt(x)` | Wurzel |
| `math.pi` | π |
| `math.ceil(x)` / `math.floor(x)` | auf- / abrunden |
| `math.pow(x, y)` / `math.fabs(x)` | wie `pow` / `abs`, immer `float` |
| `math.sin/cos/tan` | Trigonometrie (Radiant) |
| `math.radians` / `math.degrees` | Grad ↔ Radiant |

```python
print(math.pi * 4 ** 2)         # Kreisfläche
print(math.sqrt(abs(-49)))      # verschachtelt: innen zuerst
```

Lange Rechnungen in **Zwischenschritte** aufteilen (Clean Code).

---

## Beispiele

```python
# Rabatt
discount = price * percent / 100
final_price = price - discount

# BMI
bmi = weight / (height ** 2)

# Celsius → Fahrenheit
fahrenheit = celsius * 9/5 + 32
```

**Flaschenpost-Aufgabe:** Gesamtbetrag = Anzahl × Rückgabewert, neue Flaschen = Betrag `//` Preis, Restgeld = Betrag `%` Preis.

---

→ [[02 - Variablen und Datentypen]] · [[04 - Boolsche Operatoren]]
