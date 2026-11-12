# Variablen und Datentypen

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Variablen #Datentypen #Casting

---

## Variablen

Eine Variable ist ein Platzhalter für einen Wert, wie eine beschriftete Schublade.

```python
name = "Arthur"      # = ist der Zuweisungsoperator
x = 5
print(name)
```

- Name links, Wert rechts
- Code läuft von oben nach unten, eine Variable gibt es erst **nach** dem Erstellen
- Vorteile: lesbar, nur an einer Stelle ändern

```python
user_input = input("Eingabe: ")
```

---

## Namen

Ein Name ist ein einziges Wort ohne Leerzeichen.

| Stil | Beispiel | Wo |
|------|----------|-----|
| **snake_case** | `user_name` | Python (Variablen, Funktionen) |
| camelCase | `userName` | JavaScript, Java |
| PascalCase | `UserName` | C#, Klassen in Python |
| kebab-case | `user-name` | URLs, CSS |

Sprechende Namen: `user_name` statt `b`.

---

## Datentypen

| Typ | Beispiel |
|-----|----------|
| `str` | `"Hello"` |
| `int` | `42` |
| `float` | `3.1415` |
| `bool` | `True` / `False` (gross schreiben!) |

- `+` verbindet Strings: `"Hello, " + "World!"`
- Floats können kleine Rundungsfehler haben (`0.1 + 0.2`)
- `type(x)` zeigt den Typ

---

## Dynamische Typisierung

Der Typ hängt vom aktuellen Wert ab. Neue Zuweisung überschreibt Wert und Typ.

```python
x = 42       # int
x = "vier"   # str
```

---

## Casting

| Funktion | Ergebnis |
|----------|----------|
| `int()` | ganze Zahl |
| `float()` | Kommazahl |
| `str()` | Text |
| `bool()` | Wahrheitswert (nicht-leerer String = `True`) |

**`input()` gibt immer einen String zurück.** Zum Rechnen umwandeln:

```python
zahl = int(input("Zahl: "))
print(42 + zahl)
```

---

→ [[01 - Python und IDE]] · [[03 - Mathematische Operatoren]] · [[10 - Characters und Strings]]
