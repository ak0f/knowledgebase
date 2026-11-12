# Characters und Strings

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #String #Character #f-String

---

## Lernziele

- [ ] Character und String unterscheiden
- [ ] Strings erstellen (ein- und mehrzeilig)
- [ ] Auf Zeichen per Index zugreifen
- [ ] Strings verketten und mit Methoden bearbeiten
- [ ] f-Strings und Escape Characters verwenden

---

## Character und String

- **Character** = kleinstes Textelement (Buchstabe, Ziffer, Satzzeichen, Leerzeichen)
- In Python gibt es keinen eigenen Char-Typ: `'a'` ist ein `str` der Länge 1
- **String** = Zeichenkette in Anführungszeichen (`'...'` oder `"..."`, einheitlich öffnen/schliessen)

```python
single_letter = "A"
one_word = "Hallo"
numbers = "1234"
empty = ""
```

### Mehrzeilige Strings

```python
string3 = '''Das ist ein
mehrzeiliger String'''
string4 = """Das ist auch
ein mehrzeiliger String"""
```

### Eingabe

`input()` liefert **immer** einen String (auch bei `42` → `"42"`).

```python
user_input = input("Gib deinen Namen ein: ")
print("Du hast eingegeben: " + user_input)
```

**Übung:** Name und Stimmung abfragen und eine freundliche Antwort ausgeben, die beides enthält.

```python
name = input("Wie heisst du? ")
mood = input("Wie geht's dir heute? ")
print(f"Hallo {name}! Schön, dass es dir {mood} geht.")
```

---

## Zugriff auf Zeichen

Index in eckigen Klammern, Zählung startet bei **0**. Negative Indizes zählen von hinten.

```python
text = "Python"
print(text[0])    # P
print(text[1])    # y
print(text[-1])   # n
```

```
 P   y   t   h   o   n
 0   1   2   3   4   5
-6  -5  -4  -3  -2  -1
```

- Index ausserhalb → `IndexError` (`"Hi"[5]`)
- Länge: `len("Python")` → 6
- Letztes Zeichen: `text[len(text) - 1]` oder einfacher `text[-1]`
- Länge zählt ab 1, Indizes ab 0 → letzter Index = `len - 1`

---

## String-Operationen

### Verketten mit +

```python
result = "Hallo" + " " + "Welt"
```

Nur String + String. Zahlen zuerst mit `str()` casten:

```python
number = str(123)
print("Die Zahl ist: " + number)
```

### Nützliche Methoden

| Methode | Wirkung | Beispiel |
|---------|---------|----------|
| `.lower()` | alles klein | `"Python".lower()` → `python` |
| `.upper()` | alles gross | `"Python".upper()` → `PYTHON` |
| `.strip()` | Leerzeichen am Anfang/Ende entfernen | `"  Hallo  ".strip()` → `Hallo` |
| `.replace(a, b)` | Teilstring ersetzen | `"Hallo Welt".replace("Welt", "Python")` |
| `len(s)` | Anzahl Zeichen | `len("Python")` → 6 |

---

## f-Strings

Variablen und Ausdrücke direkt in `{}` einbetten.

```python
name = "Anna"
alter = 25
print(f"Mein Name ist {name} und ich bin {alter} Jahre alt.")
```

**Vorteile:**

1. **Lesbarkeit**, fast wie normaler Text, kein `str()` nötig
2. **Wartbarkeit**, neue Variablen leicht ergänzen
3. **Effizienz**, meist schneller als `+`

```python
price = 49.95
print(f"Der Preis beträgt {price:.2f} Franken.")
```

---

## Escape Characters

Backslash `\` + Zeichen, um Sonderzeichen darzustellen.

| Zeichen | Bedeutung |
|---------|-----------|
| `\\` | Backslash |
| `\'` | einfaches Anführungszeichen |
| `\"` | doppeltes Anführungszeichen |
| `\n` | neue Zeile |
| `\t` | Tabulator |

```python
text = "Erste Zeile\nZweite Zeile\tmit Tabulator\nMit \"Anführungszeichen\""
print(text)
```

---

## Verknüpfungen

→ [[02 - Variablen und Datentypen]]
→ [[11 - Strings Extended]]
→ [[12 - Listen und Dictionaries]]
