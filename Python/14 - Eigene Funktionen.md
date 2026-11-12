# Eigene Funktionen schreiben

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #def #return #Parameter

---

## Lernziele

- [ ] Funktionen mit `def` definieren und aufrufen
- [ ] Parameter für generische Funktionen verwenden
- [ ] Mit `return` Ergebnisse zurückgeben
- [ ] Funktionen kombinieren

---

## Grundstruktur

```python
def funktionsname(parameter):
    # eingerückter Funktionskörper
    ...
```

- `def` + Name + Klammern + `:`
- Der Block darunter läuft **nur**, wenn die Funktion **aufgerufen** wird

```python
def hallo_welt():
    print("Hallo, Welt!")

hallo_welt()   # erst hier läuft der Code
```

---

## Parameter

Parameter machen Funktionen **generisch**: Sie funktionieren mit verschiedenen Werten, ohne dass man sie ändern muss. Reihenfolge und Format der Argumente müssen stimmen.

```python
def berechne_gesamtpreis(preis_pro_stueck, anzahl):
    gesamt = preis_pro_stueck * anzahl
    print(f"Gesamtpreis: {gesamt} CHF")

berechne_gesamtpreis(2.50, 4)    # 10.0 CHF
berechne_gesamtpreis(1.20, 10)   # 12.0 CHF
```

### Übungen

- `zahlen_check()`: Zahlen 1 bis 10 durchgehen, ausgeben ob ohne Rest durch 3 teilbar
- `aufgaben_status()`: Dictionary (Aufgabe → True/False) mit `for` durchlaufen
- `begruesse(name)`, `berechne_flaeche(breite, hoehe)`, `praege_muenzen(betrag, wert)` mit Eingaben per `input()`

---

## Rückgabewerte

Mit `return` ein Ergebnis an den Aufrufer zurückgeben, statt es nur auszugeben.

```python
def berechne_quadrat(x):
    return x * x

quadr = berechne_quadrat(5)                  # speichern: 25
summe = quadr + berechne_quadrat(3)          # weiterrechnen: 34
berechne_quadrat(4)                          # ignorieren (erlaubt)
```

**Prinzipien:**

- **Wiederverwendbarkeit:** Ergebnis lässt sich überall weiterverarbeiten
- **Single Responsibility:** jede Funktion macht genau **eine** Aufgabe (z. B. rechnen, nicht ausgeben)
- Rückgabewert darf ignoriert werden

---

## Beispiel: Rabattberechnung

```python
def discount_price(price, percentage):
    return price * (1 - percentage / 100)

def total_purchase(prices, percentage):
    total = 0
    for price in prices:
        total += discount_price(price, percentage)   # Formel nicht neu schreiben!
    return total

print(discount_price(50.0, 15))                    # 42.5
print(total_purchase([50.0, 30.0, 20.0], 15))      # 85.0
```

---

## Verknüpfungen

→ [[13 - Funktionsaufrufe]]
→ [[15 - Eigene range-Funktionen]]
→ [[09 - Indents und Scopes]]
