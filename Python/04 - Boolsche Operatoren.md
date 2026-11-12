# Boolsche Operatoren

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Boolean #Vergleich #Logik

---

## Vergleichsoperatoren

Ergebnis ist `True` oder `False`.

| Operator | Bedeutung |
|----------|-----------|
| `==` | gleich |
| `!=` | ungleich |
| `>` `<` | grösser, kleiner |
| `>=` `<=` | grösser/gleich, kleiner/gleich |

`=` weist zu, `==` vergleicht.

---

## not, and, or, xor

| A | B | not A | A and B | A or B | A xor B |
|---|---|-------|---------|--------|---------|
| F | F | T | F | F | F |
| F | T | T | F | T | T |
| T | F | F | F | T | T |
| T | T | F | T | T | F |

- `and`: beide wahr
- `or`: mindestens einer wahr
- `xor`: genau einer wahr, in Python `a != b`
- `nor`: `not (a or b)`, nur wahr wenn beide falsch

---

## Ausdrücke auswerten

1. Innere Klammern zuerst
2. `not` zuerst einzeln ausrechnen
3. Zwischenschritte aufschreiben

**Beispiel:** `(A and not B) or (C and A)` mit A=True, B=False, C=True

- `not B` = True
- `A and not B` = True
- `C and A` = True
- True or True = **True**

**Beispiel aus der Praxis:**

```python
alter = 20
hat_ticket = False
ist_mitarbeiter = True
gesperrt = False

not ((alter >= 18 and hat_ticket) or (ist_mitarbeiter and not gesperrt))
# (True and False) = False, (True and True) = True, False or True = True, not True = False
```

---

→ [[03 - Mathematische Operatoren]] · [[05 - Entscheidungen mit if, elif und else]] · [[07 - While-Schleife]]
