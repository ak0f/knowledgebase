# Indents und Scopes

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Indent #Scope #Eigenrecherche

> Im Kurs war das eine **Eigenrecherche** (Notizen für die Klassendiskussion). Die Inhalte hier sind eine Zusammenfassung des Standardwissens.

---

## Fragen der Recherche

- Scopes: Was versteht man darunter?
- Indents: Welche Rolle spielen Einrückungen?
- Was passiert bei unterschiedlichen Einrückungen?

---

## Indents (Einrückungen)

- Python nutzt **Einrückungen statt geschweifter Klammern**, um Blöcke zu bilden
- Alles, was zusammengehört (nach `if`, `for`, `while`, `def`), wird gleich weit eingerückt
- Standard: **4 Leerzeichen** pro Ebene (PyCharm macht das mit `Tab` automatisch)
- Nach einem `:` folgt immer ein eingerückter Block

```python
if x > 5:
    print("gross")      # gehört zum if
    print("noch drin")  # gehört zum if
print("immer")          # gehört nicht mehr zum if
```

### Inkonsistente Einrückung

```python
if x > 5:
    print("a")
      print("b")   # IndentationError: unexpected indent
```

- Zu viel/zu wenig Einrückung → `IndentationError`
- Tabs und Leerzeichen mischen → `TabError`
- Falsche Einrückung kann auch **keinen Fehler** geben, aber die Logik verändern (Zeile gehört dann zu einem anderen Block)

---

## Scopes (Gültigkeitsbereiche)

Ein **Scope** ist der Bereich im Code, in dem eine Variable sichtbar und nutzbar ist.

| Scope | Beschreibung |
|-------|--------------|
| **Lokal** | Variable innerhalb einer Funktion, nur dort gültig |
| **Global** | Variable ausserhalb von Funktionen, überall lesbar |

```python
name = "Anna"            # global

def greet():
    message = "Hallo"    # lokal
    print(message, name)

greet()
print(message)           # NameError: message existiert hier nicht
```

- Lokale Variablen verschwinden, wenn die Funktion endet
- Wird in einer Funktion einer Variable ein Wert zugewiesen, entsteht eine **neue lokale** Variable (auch bei gleichem Namen wie eine globale)
- Mit `global name` könnte man die globale ändern, besser ist es aber, Werte per **Parameter** und **return** weiterzugeben
- Block-Einrückung (`if`, `for`) erzeugt in Python **keinen** eigenen Scope: Eine Variable aus einem `for`-Block ist danach noch sichtbar

---

## Verknüpfungen

→ [[05 - Entscheidungen mit if, elif und else]]
→ [[14 - Eigene Funktionen]]
→ [[18 - Debugging]]
