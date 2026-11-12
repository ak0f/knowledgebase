# Listen und Dictionaries

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Liste #Dictionary #Datenstrukturen

---

## Lernziele

- [ ] Eigenschaften von Listen nennen
- [ ] Listen erstellen, lesen und verändern
- [ ] Nützliche Listenfunktionen anwenden
- [ ] Dictionaries mit Schlüssel-Wert-Paaren nutzen

---

## Listen

Geordnete Sammlung von Elementen, vergleichbar mit einer Einkaufsliste.

| Eigenschaft | Bedeutung |
|-------------|-----------|
| Geordnet | Reihenfolge bleibt erhalten |
| Veränderbar (mutable) | Elemente hinzufügen, entfernen, ändern |
| Flexibel | verschiedene Datentypen gemischt möglich |
| Indizierbar | Zugriff über Index, **erster Index ist 0** |
| Iterierbar | mit `for` durchgehbar |

### Erstellen

```python
empty_list = []
numbers = [1, 2, 3, 4, 5]
names = ["Alice", "Bob", "Charlie"]
things = [10, "Hallo", True, 3.14]
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

### Zugriff

```python
fruits = ["Apfel", "Banane", "Kirsche", "Dattel"]
print(fruits[0])    # Apfel
print(fruits[-1])   # Dattel (letztes)
print(fruits[-2])   # Kirsche
fruits[4]           # IndexError!

matrix[0][0]        # 1
matrix[1][2]        # 6
```

### Manipulieren

| Methode | Wirkung |
|---------|---------|
| `append(x)` | Element am Ende anfügen |
| `insert(i, x)` | Element an Position i einfügen |
| `liste1 + liste2` | neue Liste aus beiden (Originale bleiben) |
| `remove(x)` | erstes Vorkommen von x entfernen (ValueError wenn nicht da) |
| `pop(i)` | Element an Index i entfernen und zurückgeben (ohne i: das letzte) |
| `clear()` | alle Elemente entfernen |
| `index(x)` | Index von x (ValueError wenn nicht da) |
| `fruits[1] = "Birne"` | Element ändern |
| `fruits[0:2] = ["Orange", "Zitrone"]` | Bereich (Slice) ändern |

```python
fruits = ["Apfel", "Banane"]
fruits.append("Kirsche")
fruits.insert(1, "Birne")
removed = fruits.pop(1)
```

### Nützliche Funktionen

```python
number_list = [10, 5, 20, 15, 25, 8]
len(number_list)      # 6
max(number_list)      # 25
min(number_list)      # 5
sum(number_list)      # 83

copy_list = number_list.copy()
copy_list.sort()      # aufsteigend sortieren
copy_list.reverse()   # umkehren

if "Banane" in fruits:
    print("Ja, Banane ist in der Liste!")
```

---

## Dictionaries

Sammlung von **Schlüssel-Wert-Paaren** (key-value), wie ein Wörterbuch. Zugriff über den Schlüssel, nicht über einen Index.

| Eigenschaft | Bedeutung |
|-------------|-----------|
| Veränderbar | Paare hinzufügen, ändern, löschen |
| Schlüssel einzigartig | gleicher Schlüssel überschreibt den alten Wert |
| Schlüssel unveränderlich | meist Strings oder Zahlen |
| Werte | beliebiger Datentyp |
| Reihenfolge | bleibt nach dem Hinzufügen erhalten, kein Index-Zugriff |

```python
person = {
    "name": "Alice",
    "age": 17,
    "city": "Bern",
    "job_title": "Softwareentwicklerin"
}
```

### Zugriff

```python
print(person["name"])           # Alice
person["salary"]                # KeyError!

person.get("salary")            # None
person.get("salary", 0)         # 0 (Standardwert)
```

`get()` ist **sicherer** als eckige Klammern.

### Hinzufügen, ändern, entfernen

```python
person["email"] = "alice@example.com"   # neu
person["age"] = 18                      # ändern
del person["age"]                       # entfernen
city = person.pop("city")               # entfernen + zurückgeben
person.clear()                          # alles löschen
```

---

## Liste vs. Dictionary

| | Liste | Dictionary |
|---|-------|-----------|
| Klammern | `[ ]` | `{ }` |
| Zugriff | Index (`list[0]`) | Schlüssel (`dict["name"]`) |
| Inhalt | Elemente | Schlüssel-Wert-Paare |
| Beispiel | Einkaufsliste | Wörterbuch, Personendaten |

---

## Verknüpfungen

→ [[06 - For-Schleife]]
→ [[11 - Strings Extended]]
→ [[13 - Funktionsaufrufe]]
