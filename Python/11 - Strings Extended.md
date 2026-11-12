# Strings Extended

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #String #Dateien #split #join

---

## Lernziele

- [ ] Textdateien schreiben, lesen und anhängen
- [ ] `.format()` und f-Strings vergleichen
- [ ] Texte durchsuchen (`in`, `find`, `index`)
- [ ] Strings und Listen mit `split()` / `join()` kombinieren
- [ ] Zeichen ersetzen, prüfen und zählen

---

## Dateien schreiben und lesen

```python
# Schreiben (überschreibt!)
with open("example.txt", "w") as file:
    file.write("Dies ist der erste Satz.\n")
    file.write("Dies ist der zweite Satz.")

# Alles lesen
with open("example.txt", "r") as file:
    text = file.read()
    print(text)

# Zeilenweise lesen
with open("example.txt", "r") as file:
    for line in file:
        print(line, end="")
```

- `end=""` verhindert doppelte Zeilenumbrüche (jede Zeile endet schon mit `\n`)
- `with` schliesst die Datei **automatisch**, auch bei Fehlern (empfohlen statt `open()` + `close()`)
- Wofür: Logs, Einstellungen, Import/Export, kleine JSON-Datenbanken

### Modi

| Modus | Bedeutung | Bei existierender Datei |
|-------|-----------|--------------------------|
| `"r"` | read (lesen) | liest den Inhalt |
| `"w"` | write (schreiben) | **löscht** den bisherigen Inhalt |
| `"a"` | append (anhängen) | hängt unten an |

```python
name = input("Wie heisst du? ")
with open("log.txt", "a") as file:
    file.write(f"{name} hat das Programm gestartet.\n")
```

> Auch beim Anhängen `\n` verwenden, sonst kleben die Einträge aneinander.

**Übung Begrüssungs-Generator:** Vorname, Nachname, Motto, Geburtsjahr abfragen → f-String-Text → in `greetings.txt` speichern (`"w"`, dann `"a"`) → Datei wieder einlesen und ausgeben.

---

## String-Formatierung mit .format()

```python
print("Hallo, {}!".format("Sam"))
print("{} ist {} Jahre alt.".format("Anna", 25))
print("{1} ist {0} Jahre alt.".format(25, "Luca"))
print("Name: {name}, Alter: {age}".format(name="Maya", age=30))
```

| Methode | Vorteil | Beispiel |
|---------|---------|----------|
| f-String | kürzer, lesbarer | `f"Hallo {name}"` |
| `.format()` | flexibler, kompatibel (alter Code, Templates) | `"Hallo {}".format(name)` |

---

## Texte durchsuchen

| Methode | Rückgabe | Bei "nicht gefunden" |
|---------|----------|----------------------|
| `in` | `True` / `False` | `False` |
| `.find()` | Index | `-1` |
| `.index()` | Index | **ValueError** |

```python
text = "Heute ist ein schöner Tag"
print("Tag" in text)         # True
print(text.find("schön"))    # 15
print(text.find("cool"))     # -1
print(text.index("ein"))     # Index oder ValueError
```

---

## Zeilen und Wörter

```python
text = "Zeile 1\nZeile 2\nZeile 3"
lines = text.splitlines()    # ['Zeile 1', 'Zeile 2', 'Zeile 3']
print(len(lines))            # 3

words = "Das ist ein einfacher Text".split()
print(f"Anzahl Wörter: {len(words)}")
```

---

## Strings und Listen kombinieren

```python
zeile = "Max;Meier;1999"
teile = zeile.split(";")      # ['Max', 'Meier', '1999']

namen = "Anna,Ben,Clara,David"
liste = namen.split(",")
for name in liste:
    if name.startswith("A"):
        print(f"{name} beginnt mit A")
print(", ".join(liste))       # Liste wieder zu String
```

- `split(trenner)` → String zu Liste
- `trenner.join(liste)` → Liste zu String

---

## Zeichen ersetzen, filtern, säubern

| Methode | Wirkung |
|---------|---------|
| `.capitalize()` | erster Buchstabe gross |
| `.title()` | jedes Wort gross |
| `.isdigit()` | nur Ziffern? |
| `.isalpha()` | nur Buchstaben? |
| `.startswith(x)` | beginnt mit x? |

```python
raw = "   Passwort123  "
clean = raw.strip().lower()   # Methoden kombinieren
```

---

## Zeichenstatistik

```python
print("Banane".count("a"))   # 2

# Häufigkeit speichern (Dictionary)
text = "Apfelsaft"
counter = {}
for char in text.lower():
    if char in counter:
        counter[char] += 1
    else:
        counter[char] = 1
print(counter)
```

---

## Verknüpfungen

→ [[10 - Characters und Strings]]
→ [[12 - Listen und Dictionaries]]
→ [[16 - Stdin und Stdout]]
