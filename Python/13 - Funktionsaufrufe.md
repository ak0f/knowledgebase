# Funktionsaufrufe

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Funktionen #Parameter #Rückgabewert

---

## Lernziele

- [ ] Erklären, was eine Funktion ist und wozu sie nützlich ist
- [ ] Funktionsname, Parameter, Argument und Funktionskörper unterscheiden
- [ ] Globale und objektgebundene Funktionen (Methoden) unterscheiden
- [ ] Ausgeben (`print`) von Zurückgeben (`return`) unterscheiden

---

## Was ist eine Funktion?

> Eine Funktion ist ein **benannter Codeblock**, der eine bestimmte Aufgabe übernimmt und überall aufgerufen werden kann.

Wie ein Werkzeug oder ein Kaffeeautomat: Knopf drücken (aufrufen), der Rest läuft von selbst.

```python
print("Hallo Bbc")   # print = vordefinierte Funktion, "Hallo Bbc" = Argument
```

---

## Anatomie einer Funktion

| Teil | Beschreibung |
|------|--------------|
| **Funktionsname** | Name, mit dem man sie aufruft (`print`) |
| **Parameter** | Platzhalter in der Definition (optional) |
| **Funktionskörper** | eingerückter Codeblock, der beim Aufruf läuft |

| Begriff | Bedeutung | Beispiel |
|---------|-----------|----------|
| **Parameter** | Platzhalter in der **Definition** | `def begruessen(name):` |
| **Argument** | konkreter Wert beim **Aufruf** | `begruessen("Anna")` |

> Parameter = leere Schublade, Argument = was man hineinlegt.

```python
def begruessen(name):            # begruessen = Name, name = Parameter
    print("Hallo, " + name + "!")  # Funktionskörper

begruessen("Lisa")               # Hallo, Lisa!
```

---

## Warum Funktionen?

| Vorteil | Bedeutung |
|---------|-----------|
| **Wiederverwendbarkeit** | einmal schreiben, beliebig oft aufrufen |
| **Lesbarkeit** | Code in klar benannte Bausteine zerlegt |
| **Wartbarkeit** | Änderung nur an einer Stelle nötig |
| **Modularität** | grosse Probleme in kleine Teilprobleme zerlegen |

```python
def is_grown_up(age):
    return age >= 18      # Grenze nur hier ändern

if is_grown_up(17):
    print("Volljährig")
else:
    print("Nicht volljährig")
```

---

## Globale Funktionen vs. Methoden

| Globale Funktion | Objektgebundene Funktion (Methode) |
|------------------|------------------------------------|
| `print("Hallo")` | `"Hallo".lower()` |
| `len([1, 2, 3])` | `[1, 2, 3].count(2)` |

Methoden hängen mit einem **Punkt** am Objekt.

Manche geben ein **neues Ergebnis** zurück, andere **verändern das Objekt**:

| Methode | Objekt | Rückgabewert? | Verändert Objekt? |
|---------|--------|---------------|-------------------|
| `"Hallo".lower()` | String | Ja (String) | Nein |
| `"Hallo Welt".split()` | String | Ja (Liste) | Nein |
| `[3, 2, 1].sort()` | Liste | Nein | **Ja** |
| `[1, 2, 3].append(4)` | Liste | Nein | **Ja** |

> Das steht in der **offiziellen Python-Dokumentation**: `docs.python.org/3/library/functions.html`. Nachschlagen ist normal.

---

## Rückgabewerte

**Ausgeben ≠ Zurückgeben**

- `print()` zeigt etwas in der Konsole an (kein Rückgabewert zum Weiterverwenden)
- `return` gibt ein Ergebnis an den Aufrufer zurück

```python
result = max(5, 4)     # nichts auf der Konsole, 5 wird gespeichert
print(result)          # 5

print(max(5, 4))       # verschachtelt: innen zuerst, dann aussen
```

Auswertung von innen nach aussen, wie in der Mathematik.

---

## Verknüpfungen

→ [[12 - Listen und Dictionaries]]
→ [[14 - Eigene Funktionen]]
→ [[15 - Eigene range-Funktionen]]
