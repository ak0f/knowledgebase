# Strings Extended

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #String #Dateien #split #join

---

## Dateien

```python
with open("example.txt", "w") as file:    # w = überschreibt
    file.write("Erster Satz.\n")

with open("example.txt", "a") as file:    # a = hängt an
    file.write("Zweiter Satz.\n")

with open("example.txt", "r") as file:    # r = lesen
    text = file.read()

with open("example.txt", "r") as file:
    for line in file:
        print(line, end="")               # end="" gegen doppelte Leerzeile
```

- `with` schliesst die Datei automatisch (besser als `open()` + `close()`)
- `\n` = Zeilenumbruch, beim Anhängen nicht vergessen
- Wofür: Logs, Einstellungen, Import/Export

---

## .format()

```python
"Hallo, {}!".format("Sam")
"{1} ist {0} Jahre alt.".format(25, "Luca")
"Name: {name}, Alter: {age}".format(name="Maya", age=30)
```

f-String ist kürzer, `.format()` ist kompatibler (alter Code, Templates).

---

## Suchen

| Methode | Rückgabe | Nicht gefunden |
|---------|----------|----------------|
| `"x" in text` | `True` / `False` | `False` |
| `text.find("x")` | Index | `-1` |
| `text.index("x")` | Index | `ValueError` |

---

## Zeilen, Wörter, Listen

```python
text.splitlines()          # in Zeilen
len(text.split())          # Anzahl Wörter
"Max;Meier;1999".split(";")  # ['Max', 'Meier', '1999']
", ".join(liste)           # Liste → String
```

---

## Prüfen und säubern

| Methode | Wirkung |
|---------|---------|
| `.capitalize()` / `.title()` | erster Buchstabe / jedes Wort gross |
| `.isdigit()` / `.isalpha()` | nur Ziffern / nur Buchstaben? |
| `.startswith(x)` | beginnt mit x? |
| `.count(x)` | wie oft kommt x vor |

```python
clean = "  Passwort123 ".strip().lower()    # Methoden kombinieren
```

**Zeichen zählen mit Dictionary:**

```python
counter = {}
for char in "Apfelsaft".lower():
    counter[char] = counter.get(char, 0) + 1
```

---

→ [[10 - Characters und Strings]] · [[12 - Listen und Dictionaries]] · [[16 - Stdin und Stdout]]
