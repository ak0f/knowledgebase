# Mathematische Operatoren

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Mathe #Operatoren #math #Runden

---

## Lernziele

- [ ] Mit int und float rechnen
- [ ] `//` (ganzzahlige Division) und `%` (Modulo) anwenden
- [ ] Eingaben mit `int()` / `float()` umwandeln und damit rechnen
- [ ] Mit `round()` und f-Strings runden und formatieren
- [ ] Mathematische Funktionen und die Bibliothek `math` nutzen

---

## Zahlentypen

```python
zahl1 = 5          # int
preis = 19.95      # float (Punkt, kein Komma!)
print(type(preis)) # <class 'float'>
```

---

## Grundrechenarten

| Operator | Bedeutung | Beispiel |
|----------|-----------|----------|
| `+` | Addition | `5 + 3` → 8 |
| `-` | Subtraktion | `10 - 4` → 6 |
| `*` | Multiplikation | `6 * 2` → 12 |
| `/` | Division | `8 / 2` → 4.0 |
| `//` | Ganzzahlige Division | `7 // 2` → 3 |
| `%` | Modulo (Rest) | `7 % 2` → 1 |
| `**` | Potenz | `2 ** 3` → 8 |

- `/` ergibt **immer** einen float
- Punkt vor Strich, Klammern zuerst

```python
print(10 + 2 * 5)     # 20
print((10 + 2) * 5)   # 60
```

---

## Ganzzahlige Division und Modulo

```python
minutes = 125
hours = minutes // 60              # 2
remaining_minutes = minutes % 60   # 5
print(f"{minutes} Minuten sind {hours} Stunden und {remaining_minutes} Minuten.")
```

**Wofür?**

- Uhrzeit umrechnen
- Gerade/ungerade prüfen: `x % 2 == 0`
- In Schleifen jeden 5. Schritt abfragen
- Gruppen, Seitenumbrüche

---

## Rechnen mit Eingaben

`input()` liefert immer einen **String** → umwandeln mit `int()` oder `float()`.

```python
length = float(input("Länge: "))
width = float(input("Breite: "))
area = length * width
print(f"Die Fläche beträgt: {area} m2")
```

> Bei Eingaben, die keine Zahl sind, gibt es einen Fehler. Das fängt man später mit `try/except` ab.

---

## Runden und Formatieren

```python
value = 3.14159
print(round(value))      # 3
print(round(value, 2))   # 3.14
```

**f-String Formatierung:**

```python
price = 19.9999
print(f"Preis: {price:.2f} CHF")   # Preis: 20.00 CHF
```

- `:` leitet die Formatangabe ein
- `.2f` = zwei Nachkommastellen als float

---

## Eingebaute Funktionen

| Funktion | Beschreibung | Beispiel |
|----------|--------------|----------|
| `abs(x)` | Betrag | `abs(-7)` → 7 |
| `pow(x, y)` | Potenz | `pow(2, 3)` → 8 |
| `min(...)` | kleinster Wert | `min(5, 2, 9, -1)` → -1 |
| `max(...)` | grösster Wert | `max(5, 2, 9, -1)` → 9 |
| `sum(liste)` | Summe | `sum([5, 8, 2])` → 15 |
| `round(x, n)` | runden | `round(3.14159, 2)` → 3.14 |

---

## Bibliothek math

```python
import math
```

| Funktion | Beschreibung |
|----------|--------------|
| `math.sqrt(x)` | Quadratwurzel |
| `math.pow(x, y)` | Potenz (immer float) |
| `math.pi` | Kreiszahl π |
| `math.ceil(x)` | aufrunden |
| `math.floor(x)` | abrunden |
| `math.fabs(x)` | Betrag (immer float) |
| `math.log(x)` / `math.log10(x)` | Logarithmus |
| `math.sin/cos/tan(x)` | Trigonometrie (Radiant!) |
| `math.radians(x)` / `math.degrees(x)` | Grad ↔ Radiant |

```python
import math
radius = 4
area = math.pi * radius ** 2
print(f"Die Kreisfläche beträgt: {area:.2f}")
```

---

## Verschachtelte Ausdrücke

```python
import math
value = -49
print(math.sqrt(abs(value)))   # 7.0 (zuerst abs, dann sqrt)
```

Besser lesbar mit **Zwischenresultaten** (Clean Code):

```python
gross_price = 120
discount_percent = 15
discount = gross_price * discount_percent / 100
net_price = gross_price - discount
print(f"Nettopreis: {net_price:.2f} CHF")
```

---

## Beispiele aus dem Alltag

```python
# BMI
weight = float(input("Gewicht in kg: "))
height = float(input("Grösse in m: "))
bmi = weight / (height ** 2)
print(f"Dein BMI ist: {bmi:.2f}")

# Temperatur
celsius = float(input("Temperatur in °C: "))
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius} °C sind {fahrenheit:.1f} °F")

# Trinkgeld
bill = float(input("Rechnungsbetrag (CHF): "))
tip_percent = float(input("Trinkgeld in %: "))
tip = bill * tip_percent / 100
print(f"Total: {bill + tip:.2f} CHF")
```

---

## Übung: Flaschenpost-Rechner

1. Eingaben: Anzahl leerer Flaschen, Rückgabewert pro Flasche (z. B. 0.30), Preis einer vollen Flasche (z. B. 1.90)
2. Berechnen: Gesamtbetrag = Anzahl × Rückgabewert, neue Flaschen = Gesamtbetrag `//` Preis, Restgeld = Gesamtbetrag `%` Preis
3. Ausgabe mit f-Strings, auf 2 Nachkommastellen gerundet, englische Variablennamen

```python
bottles = int(input("Leere Flaschen: "))
deposit = float(input("Rückgabewert pro Flasche: "))
price = float(input("Preis volle Flasche: "))

total = bottles * deposit
new_bottles = int(total // price)
change = total % price
print(f"Gesamtbetrag: {total:.2f} CHF")
print(f"Neue Flaschen: {new_bottles}, Restgeld: {change:.2f} CHF")
```

---

## Verknüpfungen

→ [[02 - Variablen und Datentypen]]
→ [[04 - Boolsche Operatoren]]
→ [[16 - Stdin und Stdout]]
