# Indents und Scopes

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Indent #Scope

> Im Kurs war das eine Eigenrecherche. Das hier ist meine Zusammenfassung.

---

## Indents (Einrückungen)

- Python bildet Blöcke mit **Einrückung**, nicht mit `{ }`
- Nach `:` (bei `if`, `for`, `while`, `def`) kommt ein eingerückter Block
- Standard: **4 Leerzeichen**

```python
if x > 5:
    print("gross")      # im if
print("immer")          # nicht mehr im if
```

**Bei falscher Einrückung:**

- zu viel oder zu wenig → `IndentationError`
- Tabs und Leerzeichen gemischt → `TabError`
- manchmal kein Fehler, aber die Logik ändert sich (Zeile gehört zu einem anderen Block)

---

## Scopes (Gültigkeitsbereiche)

Der Scope ist der Bereich, in dem eine Variable gilt.

| Scope | Beschreibung |
|-------|--------------|
| **Lokal** | in einer Funktion erstellt, nur dort sichtbar |
| **Global** | ausserhalb von Funktionen, überall lesbar |

```python
name = "Anna"            # global

def greet():
    message = "Hallo"    # lokal
    print(message, name)

greet()
print(message)           # NameError
```

- Lokale Variablen verschwinden nach der Funktion
- Eine Zuweisung in der Funktion erstellt eine **neue lokale** Variable
- Besser als `global`: Werte über **Parameter** und **return** weitergeben
- `if` und `for` haben **keinen** eigenen Scope

---

→ [[05 - Entscheidungen mit if, elif und else]] · [[14 - Eigene Funktionen]] · [[18 - Debugging]]
