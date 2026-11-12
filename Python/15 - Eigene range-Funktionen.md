# Eigene range()-Funktion

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Funktionen #range #Standardwert

---

## Aufgabe

`bbc_range(start, end, step)` nachbauen, ohne das eingebaute `range()`. Gibt eine **Liste** zurück.

- `end` ist nicht dabei
- `step` ist optional, **Standardwert 1**
- geht auch mit negativem `step`
- leere Liste, wenn keine gültige Reihe möglich ist

```python
bbc_range(0, 5)       # [0, 1, 2, 3, 4]
bbc_range(3, 10, 2)   # [3, 5, 7, 9]
bbc_range(10, 3, -2)  # [10, 8, 6, 4]
```

**Standardwert:** `def bbc_range(start, end, step=1):`

---

## Lösungsidee

```python
def bbc_range(start, end, step=1):
    result = []
    if step == 0:
        return result
    current = start
    if step > 0:
        while current < end:
            result.append(current)
            current += step
    else:
        while current > end:
            result.append(current)
            current += step
    return result
```

**Spezialfälle zum Testen:** `step = 0` (sonst Endlosschleife), `start >= end` bei positivem step, negativer step mit `start < end`, `start == end`.

**Abgabe:** GitLab-Link, dem Coach erklären (Standardwert, Schleife, Spezialfälle).

---

→ [[14 - Eigene Funktionen]] · [[06 - For-Schleife]] · [[07 - While-Schleife]]
