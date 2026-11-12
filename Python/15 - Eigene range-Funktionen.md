# Eigene range()-Funktion

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Funktionen #range #Standardwert

---

## Aufgabe

Eine eigene Version von `range()` als Funktion `bbc_range(start, end, step)` bauen, die eine **Liste** zurückgibt.

**Anforderungen:**

1. Name: `bbc_range()`
2. Parameter: `start`, `end` (wird nicht eingeschlossen), `step` (optional, **Standardwert 1**)
3. Gibt eine Liste zurück
4. Eingebautes `range()` **nicht** verwenden, Logik mit einer Schleife
5. Funktioniert mit positivem **und** negativem `step`
6. Leere Liste, wenn keine gültige Sequenz möglich ist (z. B. `bbc_range(5, 2)`)

```python
print(bbc_range(0, 5))      # [0, 1, 2, 3, 4]
print(bbc_range(3, 10, 2))  # [3, 5, 7, 9]
print(bbc_range(10, 3, -2)) # [10, 8, 6, 4]
```

---

## Standardwert für Parameter

```python
def do_some(activity, repeat=1):
    ...
```

Wird `repeat` nicht übergeben, gilt 1.

---

## Lösungsidee

```python
def bbc_range(start, end, step=1):
    result = []
    if step == 0:
        return result            # Spezialfall: Schritt 0 wäre eine Endlosschleife
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

**Spezialfälle zum Testen:**

- `step = 0` → leere Liste (sonst Endlosschleife)
- `start >= end` mit positivem step → leere Liste
- negativer step mit `start < end` → leere Liste
- `start == end` → leere Liste

---

## Abgabe (Kurs)

- GitLab-Link zum Mini-Projekt abgeben
- Dem Coach erklären: Standardwert für `step`, Funktionsweise der Schleife, entdeckte Spezialfälle

---

## Verknüpfungen

→ [[14 - Eigene Funktionen]]
→ [[06 - For-Schleife]]
→ [[07 - While-Schleife]]
