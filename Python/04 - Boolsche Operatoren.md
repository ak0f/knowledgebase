# Boolsche Operatoren

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Boolean #Vergleich #Logik

---

## Lernziele

- [ ] Vergleichsoperatoren anwenden
- [ ] `not`, `and`, `or` und XOR erklären
- [ ] Wahrheitstabellen lesen
- [ ] Verschachtelte Ausdrücke von innen nach aussen auswerten

---

## Vergleichsoperatoren

Ergebnis ist immer `True` oder `False`.

| Operator | Bedeutung | Beispiel |
|----------|-----------|----------|
| `==` | gleich | `5 == 5` → True |
| `!=` | ungleich | `5 != 3` → True |
| `>` | grösser als | `7 > 3` → True |
| `<` | kleiner als | `2 < 5` → True |
| `>=` | grösser/gleich | `5 >= 5` → True |
| `<=` | kleiner/gleich | `3 <= 4` → True |

> `=` ist die **Zuweisung**, `==` ist der **Vergleich**.

---

## Boolesche Operatoren

### NOT – umkehren

| A | not A |
|---|-------|
| True | False |
| False | True |

### AND – beide müssen wahr sein

| A | B | A and B |
|---|---|---------|
| False | False | False |
| False | True | False |
| True | False | False |
| True | True | **True** |

### OR – mindestens einer muss wahr sein

| A | B | A or B |
|---|---|--------|
| False | False | False |
| False | True | **True** |
| True | False | **True** |
| True | True | **True** |

### XOR – genau einer muss wahr sein

In Python mit `!=` ausdrücken: `a != b`

| A | B | A XOR B |
|---|---|---------|
| False | False | False |
| False | True | **True** |
| True | False | **True** |
| True | True | False |

**NOR** = `not (a or b)`, nur wahr wenn beide falsch sind.

| Symbol | Operator |
|--------|----------|
| ¬ | NOT |
| ∧ | AND |
| ∨ | OR |
| ⊕ | XOR |

---

## Ausdrücke auswerten

**Strategie:**

1. Innere Klammern zuerst
2. `not` immer zuerst isoliert ausrechnen
3. Zwischenschritte notieren
4. Bei Unsicherheit eine Wahrheitstabelle daneben schreiben

### Beispiel 1: `(A and not B) or (C and A)`

A = True, B = False, C = True

| Schritt | Rechnung | Ergebnis |
|---------|----------|----------|
| `not B` | not False | True |
| `A and not B` | True and True | True |
| `C and A` | True and True | True |
| Gesamt | True or True | **True** |

### Beispiel 2: `(not A or B) and (C XOR not B)`

A = True, B = False, C = True

| Schritt | Rechnung | Ergebnis |
|---------|----------|----------|
| `not A` | not True | False |
| `not A or B` | False or False | False |
| `not B` | not False | True |
| `C XOR not B` | True XOR True | False |
| Gesamt | False and False | **False** |

### Beispiel 3: aus der Praxis

```python
alter = 20
hat_ticket = False
ist_mitarbeiter = True
gesperrt = False

result = not ((alter >= 18 and hat_ticket) or (ist_mitarbeiter and not gesperrt))
print(result)   # False
```

| Schritt | Ergebnis |
|---------|----------|
| `alter >= 18` | True |
| `alter >= 18 and hat_ticket` | False |
| `not gesperrt` | True |
| `ist_mitarbeiter and not gesperrt` | True |
| `(…) or (…)` | True |
| `not True` | **False** |

---

## Verknüpfungen

→ [[03 - Mathematische Operatoren]]
→ [[05 - Entscheidungen mit if, elif und else]]
→ [[07 - While-Schleife]]
