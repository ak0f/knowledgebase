# Eigene Funktionen schreiben

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #def #return #Parameter

---

## Grundstruktur

```python
def hallo_welt():
    print("Hallo, Welt!")

hallo_welt()      # erst der Aufruf führt den Code aus
```

`def` + Name + Klammern + `:`, darunter der eingerückte Block.

---

## Parameter

Machen die Funktion **generisch**: Sie geht mit verschiedenen Werten, ohne dass ich sie ändern muss. Reihenfolge der Argumente beachten.

```python
def berechne_gesamtpreis(preis_pro_stueck, anzahl):
    print(f"Gesamtpreis: {preis_pro_stueck * anzahl} CHF")

berechne_gesamtpreis(2.50, 4)    # 10.0 CHF
```

---

## return

Gibt ein Ergebnis an den Aufrufer zurück, statt es nur auszugeben.

```python
def berechne_quadrat(x):
    return x * x

quadr = berechne_quadrat(5)               # speichern
summe = quadr + berechne_quadrat(3)       # weiterrechnen
berechne_quadrat(4)                       # ignorieren geht auch
```

- **Single Responsibility:** eine Funktion macht genau eine Aufgabe (z. B. rechnen, nicht ausgeben)
- Dann kann ich das Ergebnis speichern, weiterrechnen oder ignorieren

---

## Beispiel Rabatt

```python
def discount_price(price, percentage):
    return price * (1 - percentage / 100)

def total_purchase(prices, percentage):
    total = 0
    for price in prices:
        total += discount_price(price, percentage)   # Formel nicht nochmal schreiben
    return total

total_purchase([50.0, 30.0, 20.0], 15)    # 85.0
```

---

→ [[13 - Funktionsaufrufe]] · [[15 - Eigene range-Funktionen]] · [[09 - Indents und Scopes]]
