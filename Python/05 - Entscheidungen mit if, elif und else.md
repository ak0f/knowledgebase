# Entscheidungen mit if, elif und else

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #if #elif #else

> Thema war nicht als PDF vorhanden, selbst zusammengefasst.

---

## Aufbau

```python
if bedingung:
    ...
elif andere_bedingung:
    ...
else:
    ...
```

- Nach der Bedingung kommt ein `:`
- Der Block ist **eingerückt** (4 Leerzeichen)
- Python prüft von oben nach unten und führt **nur den ersten** passenden Block aus
- `elif` darf mehrfach vorkommen, `else` nur einmal am Schluss (ohne Bedingung)

```python
note = float(input("Note: "))
if note >= 5.5:
    print("Sehr gut")
elif note >= 4.5:
    print("Gut")
elif note >= 4:
    print("Genügend")
else:
    print("Ungenügend")
```

Die **Reihenfolge** zählt: Würde `>= 4` zuerst stehen, wäre jede Note ab 4 "Genügend".

---

## Bedingungen kombinieren

```python
if alter >= 18 and hat_ticket:
    ...
if alter < 6 or alter > 65:
    ...
if not hat_ticket:
    ...
if 1 <= x <= 6:        # verketteter Vergleich
    ...
```

Strings vergleiche ich am besten mit `.lower().strip()`.

**Verschachtelt** geht auch, ist aber oft mit `and` lesbarer:

```python
if age >= 18 and has_license:
    print("Du darfst fahren.")
```

---

## Was gilt als falsch?

`False`, `0`, `0.0`, `""`, `[]`, `{}`, `None`. Alles andere ist wahr.

```python
name = input("Name: ")
if name:
    print(f"Hallo {name}")
```

---

## Typische Fehler

| Fehler | Richtig |
|--------|---------|
| `if x = 5:` | `if x == 5:` |
| `:` vergessen | `if x > 5:` |
| `else if` | `elif` |
| `"5" > 3` (input ist String) | `int(input())` |
| falsche Einrückung | immer 4 Leerzeichen |

Schaltjahr: `(year % 4 == 0 and year % 100 != 0) or year % 400 == 0`

---

→ [[04 - Boolsche Operatoren]] · [[06 - For-Schleife]] · [[21 - Einstieg UML]]
