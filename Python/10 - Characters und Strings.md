# Characters und Strings

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #String #f-String

---

## Character und String

- **Character** = einzelnes Zeichen (Buchstabe, Ziffer, Satzzeichen, Leerzeichen)
- In Python gibt es keinen Char-Typ: `'a'` ist ein `str` der Länge 1
- **String** = Zeichenkette in `'...'` oder `"..."` (einheitlich öffnen und schliessen)

```python
word = "Hallo"
empty = ""
text = """Das ist ein
mehrzeiliger String"""
```

`input()` gibt immer einen String zurück, auch bei `42` → `"42"`.

---

## Zugriff per Index

Zählung startet bei **0**, negative Indizes zählen von hinten.

```
 P   y   t   h   o   n
 0   1   2   3   4   5
-6  -5  -4  -3  -2  -1
```

```python
text = "Python"
text[0]       # P
text[-1]      # n
len(text)     # 6
text[10]      # IndexError
```

Letzter Index = `len(text) - 1`, weil die Länge bei 1 und die Indizes bei 0 starten.

---

## Operationen

```python
"Hallo" + " " + "Welt"          # verketten
"Zahl: " + str(123)             # Zahl zuerst casten
```

| Methode | Wirkung |
|---------|---------|
| `.lower()` / `.upper()` | klein / gross |
| `.strip()` | Leerzeichen am Rand entfernen |
| `.replace(a, b)` | ersetzen |
| `len(s)` | Anzahl Zeichen |

---

## f-Strings

```python
name = "Anna"
alter = 25
print(f"Mein Name ist {name} und ich bin {alter} Jahre alt.")
print(f"Preis: {49.95:.2f} Franken")
```

Besser lesbar und wartbar als `+`, und man muss nicht casten.

---

## Escape Characters

| Zeichen | Bedeutung |
|---------|-----------|
| `\n` | neue Zeile |
| `\t` | Tabulator |
| `\\` | Backslash |
| `\'` / `\"` | Anführungszeichen |

```python
print("Zeile 1\nZeile 2\tmit Tab\nMit \"Zitat\"")
```

---

→ [[02 - Variablen und Datentypen]] · [[11 - Strings Extended]] · [[12 - Listen und Dictionaries]]
