# Entscheidungen mit if, elif und else

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #if #elif #else #Verzweigung

> Dieses Thema hattest du nicht als PDF. Die Notiz ist selbst verfasst, im gleichen Stil wie die anderen.

---

## Lernziele

- [ ] `if`, `elif` und `else` anwenden
- [ ] Bedingungen mit Vergleichs- und booleschen Operatoren bauen
- [ ] Verschachtelte Entscheidungen schreiben
- [ ] Einrückungen korrekt setzen

---

## Idee

Ein Programm soll je nach Situation **verschiedene Wege** gehen. In UML ist das der **Entscheidungsknoten** (Raute), im Code die **if-Verzweigung**.

```
Bedingung wahr?  ──ja──►  Code A
        │
        └──nein──►  Code B
```

---

## if

```python
age = 20
if age >= 18:
    print("Du bist volljährig.")
```

- Nach der Bedingung steht ein **Doppelpunkt** `:`
- Der Block danach ist **eingerückt** (4 Leerzeichen)
- Der Block läuft nur, wenn die Bedingung `True` ist

---

## if ... else

```python
age = 16
if age >= 18:
    print("Volljährig")
else:
    print("Minderjährig")
```

`else` hat **keine** Bedingung. Es läuft, wenn alles davor `False` war.

---

## if ... elif ... else

Für **mehrere** Möglichkeiten. Python prüft von oben nach unten und führt **nur den ersten** passenden Block aus.

```python
note = float(input("Note (1-6): "))

if note >= 5.5:
    print("Sehr gut")
elif note >= 4.5:
    print("Gut")
elif note >= 4:
    print("Genügend")
else:
    print("Ungenügend")
```

| Teil | Anzahl | Bedingung nötig? |
|------|--------|------------------|
| `if` | genau 1 am Anfang | ja |
| `elif` | beliebig viele | ja |
| `else` | höchstens 1 am Ende | nein |

> Die **Reihenfolge** ist wichtig. Würde `note >= 4` zuerst stehen, wäre jede Note ab 4 "Genügend".

---

## Bedingungen kombinieren

```python
alter = 20
hat_ticket = True

if alter >= 18 and hat_ticket:
    print("Eintritt erlaubt")

if alter < 6 or alter > 65:
    print("Ermässigung")

if not hat_ticket:
    print("Bitte Ticket kaufen")
```

Mehr dazu: [[04 - Boolsche Operatoren]]

### Wertebereich prüfen

```python
x = 5
if 1 <= x <= 6:       # Python erlaubt verkettete Vergleiche
    print("x liegt zwischen 1 und 6")
```

### Strings vergleichen

```python
antwort = input("Weiter? (ja/nein): ").lower().strip()
if antwort == "ja":
    print("Los geht's")
```

---

## Verschachtelt

```python
age = 25
has_license = True

if age >= 18:
    if has_license:
        print("Du darfst fahren.")
    else:
        print("Du brauchst zuerst einen Führerschein.")
else:
    print("Zu jung.")
```

Oft lesbarer mit `and`:

```python
if age >= 18 and has_license:
    print("Du darfst fahren.")
```

---

## Typische Fehler

| Fehler | Beispiel | Lösung |
|--------|----------|--------|
| `=` statt `==` | `if x = 5:` → SyntaxError | `if x == 5:` |
| Doppelpunkt vergessen | `if x > 5` | `if x > 5:` |
| Falsche Einrückung | `IndentationError` | immer 4 Leerzeichen |
| `else if` statt `elif` | SyntaxError | `elif` |
| String vs. Zahl | `input()` ist ein String: `"5" > 3` → TypeError | `int(input())` |
| Falsche Reihenfolge bei `elif` | spezielle Fälle zuletzt | engste Bedingung zuerst |

### Wahrheitswerte

In einer Bedingung gelten als **falsch**: `False`, `0`, `0.0`, `""` (leerer String), `[]`, `{}`, `None`. Alles andere ist wahr.

```python
name = input("Name: ")
if name:
    print(f"Hallo {name}")
else:
    print("Du hast nichts eingegeben.")
```

---

## Übungen

1. Programm, das eine Zahl einliest und ausgibt, ob sie positiv, negativ oder null ist
2. Gerade oder ungerade (Tipp: `%`)
3. Noten-Rechner mit `elif`-Kette
4. Schaltjahr: durch 4 teilbar, aber nicht durch 100, ausser durch 400

```python
year = int(input("Jahr: "))
if (year % 4 == 0 and year % 100 != 0) or year % 400 == 0:
    print("Schaltjahr")
else:
    print("Kein Schaltjahr")
```

---

## Verknüpfungen

→ [[04 - Boolsche Operatoren]]
→ [[06 - For-Schleife]]
→ [[09 - Indents und Scopes]]
→ [[21 - Einstieg UML]]
