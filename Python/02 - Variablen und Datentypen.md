# Variablen und Datentypen

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Variablen #Datentypen #Casting

---

## Lernziele

- [ ] Variablen erstellen und verwenden
- [ ] Namenskonventionen (snake_case) anwenden
- [ ] Die 4 Datentypen int, float, str, bool kennen
- [ ] Casting mit `int()`, `float()`, `str()`, `bool()` anwenden
- [ ] Erklären, dass `input()` immer einen String liefert

---

## Was ist eine Variable?

Ein **Platzhalter** für einen Wert. Wie eine beschriftete Schublade im Speicher des PCs.

```python
x = 5            # = ist der Zuweisungsoperator
name = "Arthur"
print(name)      # Arthur
```

- Name links, Wert rechts vom `=`
- Code wird **von oben nach unten** ausgeführt, eine Variable gilt erst **nach** dem Erstellen
- Vorteile: Lesbarkeit, Wartbarkeit, Flexibilität

```python
a = 10
b = 8
c_squared = a * a + b * b
print("c squared is: ", c_squared)   # c squared is: 164
```

### Eingabe mit input()

```python
user_input = input("please enter something: ")
print("User entered: ", user_input)
```

---

## Namenskonventionen

Ein Variablenname ist **eine einzige Zeichenkette** (keine Leerzeichen).

| Stil | Beispiel | Verwendung |
|------|----------|------------|
| **snake_case** | `user_name` | Python: Variablen und Funktionen |
| camelCase | `userName` | JavaScript, Java |
| PascalCase | `UserName` | C#, in Python für Klassen |
| kebab-case | `user-name` | URLs, CSS |

> **Tipp:** sprechende Namen wählen. `user_name` statt `b`.

---

## Datentypen

| Datentyp | Beispiel | Beschreibung |
|----------|----------|--------------|
| `str` (String) | `x = "Hello World"` | Zeichenkette |
| `int` (Integer) | `x = 42` | Ganzzahl |
| `float` | `x = 3.1415` | Dezimalzahl |
| `bool` (Boolean) | `x = True` / `False` | Wahrheitswert |

- `True` und `False` immer mit **Grossbuchstaben**
- Der `+`-Operator **verbindet** Strings: `"Hello, " + "World!"`
- Floats können kleine **Rundungsfehler** haben:

```python
print(0.0001 + 0.0003)   # nicht exakt 0.0004
print(7 / 2)             # 3.5
```

---

## Dynamische Typisierung

Der Typ wird **zur Laufzeit** durch den aktuellen Wert bestimmt.

```python
x = 42       # int
x = 4.2      # float
x = "four"   # str
x = True     # bool
print(type(x))
```

Jede neue Zuweisung überschreibt Wert **und** Datentyp. (In statisch typisierten Sprachen ist der Typ fix.)

---

## Casting (Typumwandlung)

| Funktion | Ergebnis |
|----------|----------|
| `int()` | ganze Zahl |
| `float()` | Dezimalzahl |
| `str()` | Zeichenkette |
| `bool()` | Wahrheitswert |

```python
s = "123"
n = int(s)      # 123 (int)
f = float(s)    # 123.0 (float)
b = bool(s)     # True (nicht-leerer String)
```

### Casting bei input()

`input()` liefert **immer** einen `str`, auch bei Zahlen.

```python
user_input = input()
result = 42 + user_input        # Fehler! int + str

user_input_int = int(user_input)
result = 42 + user_input_int    # funktioniert
print(result)
```

---

## Verknüpfungen

→ [[01 - Python und IDE]]
→ [[03 - Mathematische Operatoren]]
→ [[10 - Characters und Strings]]
→ [[16 - Stdin und Stdout]]
