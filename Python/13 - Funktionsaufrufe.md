# Funktionsaufrufe

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Funktionen #Parameter #return

---

## Was ist eine Funktion?

Ein **benannter Codeblock**, der eine Aufgabe erledigt und den ich überall aufrufen kann. Wie ein Werkzeug oder ein Kaffeeautomat.

```python
print("Hallo Bbc")    # print = Funktion, "Hallo Bbc" = Argument
```

---

## Aufbau

| Teil | Bedeutung |
|------|-----------|
| **Funktionsname** | damit rufe ich sie auf |
| **Parameter** | Platzhalter in der Definition (optional) |
| **Argument** | konkreter Wert beim Aufruf |
| **Funktionskörper** | eingerückter Code, läuft beim Aufruf |

Parameter = leere Schublade, Argument = was ich hineinlege.

```python
def begruessen(name):            # name = Parameter
    print("Hallo, " + name + "!")

begruessen("Lisa")               # "Lisa" = Argument
```

---

## Warum Funktionen?

- **Wiederverwendbar:** einmal schreiben, oft aufrufen
- **Lesbar:** klare Namen, kleine Bausteine
- **Wartbar:** Änderung nur an einer Stelle
- **Modular:** grosses Problem in Teilprobleme zerlegen

```python
def is_grown_up(age):
    return age >= 18      # Grenze nur hier ändern
```

---

## Globale Funktionen und Methoden

| Global | Methode (am Objekt, mit Punkt) |
|--------|--------------------------------|
| `print("Hallo")` | `"Hallo".lower()` |
| `len([1, 2, 3])` | `[1, 2, 3].count(2)` |

| Methode | Gibt etwas zurück? | Verändert Objekt? |
|---------|--------------------|-------------------|
| `"Hallo".lower()` | ja (neuer String) | nein |
| `"a b".split()` | ja (Liste) | nein |
| `liste.sort()` | nein | **ja** |
| `liste.append(4)` | nein | **ja** |

Das steht in der Python-Doku (`docs.python.org/3/library/functions.html`). Nachschlagen ist normal.

---

## Rückgabewert

**Ausgeben ≠ Zurückgeben.** `print()` zeigt nur etwas an, `return` gibt ein Ergebnis zurück, das ich weiterverwenden kann.

```python
result = max(5, 4)       # nichts auf der Konsole
print(result)            # 5
print(max(5, 4))         # verschachtelt: innen zuerst
```

---

→ [[12 - Listen und Dictionaries]] · [[14 - Eigene Funktionen]] · [[15 - Eigene range-Funktionen]]
