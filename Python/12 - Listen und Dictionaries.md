# Listen und Dictionaries

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Liste #Dictionary

---

## Listen

Geordnete Sammlung, wie eine Einkaufsliste.

- **geordnet**, **veränderbar**, **indizierbar** (erster Index = 0), **iterierbar**
- verschiedene Datentypen möglich

```python
numbers = [1, 2, 3]
things = [10, "Hallo", True, 3.14]
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

fruits = ["Apfel", "Banane", "Kirsche", "Dattel"]
fruits[0]        # Apfel
fruits[-1]       # Dattel
fruits[4]        # IndexError
matrix[1][2]     # 6
```

### Methoden

| Methode | Wirkung |
|---------|---------|
| `append(x)` | hinten anfügen |
| `insert(i, x)` | an Position i einfügen |
| `a + b` | neue Liste aus beiden |
| `remove(x)` | erstes x löschen (`ValueError` wenn nicht da) |
| `pop(i)` | Element i entfernen und zurückgeben (ohne i: das letzte) |
| `clear()` | alles löschen |
| `index(x)` | Position von x |
| `liste[1] = x` | Element ändern |
| `sort()` / `reverse()` | sortieren / umkehren |
| `copy()` | Kopie |

```python
len(liste)   max(liste)   min(liste)   sum(liste)
"Banane" in fruits
```

---

## Dictionaries

Daten als **Schlüssel-Wert-Paare**, wie ein Wörterbuch.

- Schlüssel sind **einzigartig** (gleicher Schlüssel überschreibt) und unveränderlich (meist String oder Zahl)
- Zugriff über den Schlüssel, nicht über einen Index

```python
person = {"name": "Alice", "age": 17, "city": "Bern"}

person["name"]            # Alice
person["salary"]          # KeyError
person.get("salary")      # None
person.get("salary", 0)   # 0 (Standardwert)

person["email"] = "a@b.ch"   # hinzufügen
person["age"] = 18           # ändern
del person["age"]            # löschen
person.pop("city")           # löschen + zurückgeben
person.clear()               # alles löschen
```

`get()` ist sicherer als `[ ]`.

---

## Liste vs. Dictionary

| | Liste | Dictionary |
|---|-------|-----------|
| Klammern | `[ ]` | `{ }` |
| Zugriff | Index | Schlüssel |
| Inhalt | Elemente | Schlüssel-Wert-Paare |

---

→ [[06 - For-Schleife]] · [[11 - Strings Extended]] · [[13 - Funktionsaufrufe]]
