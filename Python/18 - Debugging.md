# Debugging

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Debugging #Fehler #PyCharm

---

## Fehlerarten

| Art | Bedeutung | Beispiel |
|-----|-----------|----------|
| **Syntaxfehler** | Code falsch geschrieben, läuft gar nicht | `print("Hallo"` |
| **Laufzeitfehler** | Code ok, aber beim Ausführen passiert ein Fehler | `10 / 0` |
| **Logikfehler** | läuft ohne Fehler, macht aber das Falsche | falsche Bedingung |

---

## Fehlermeldungen

| Fehler | Bedeutung |
|--------|-----------|
| `SyntaxError` | Klammer, Anführungszeichen oder `:` fehlt, `=` statt `==` |
| `IndentationError` | falsche Einrückung |
| `NameError` | Variable nicht definiert oder Tippfehler |
| `TypeError` | Typen passen nicht (`"Zahl:" + 5`) |
| `ValueError` | Typ ok, Inhalt falsch (`int("Hallo")`) |
| `IndexError` | Index ausserhalb der Liste |
| `KeyError` | Schlüssel nicht im Dictionary |
| `ZeroDivisionError` | Division durch 0 |

**Vorgehen:** Meldung **von unten nach oben** lesen (unten die Art, darüber der Ort). In kleinen Schritten testen. Fragen: *Was sollte passieren? Was passiert wirklich?*

---

## Grenzwerte

Zahlen an den Übergängen zwischen erlaubt und verboten. Hier passieren die Fehler (`<` statt `<=`).

Note 1 bis 6 → testen: **0, 1, 6, 7**.

```python
noten = ["Sehr gut", "Gut", "Befriedigend", "Ausreichend", "Mangelhaft", "Ungenügend"]
eingabe = 7

if eingabe < 1 or eingabe > 6:
    print("Bitte nur 1 bis 6.")
else:
    print(noten[eingabe - 1])
```

Ohne die Prüfung wäre `noten[6]` ein `IndexError`.

---

## Systematisch suchen

1. Was sollte passieren? (aufschreiben)
2. Programm in Teile teilen, mit `print()` prüfen
3. Eingrenzen: Unwichtiges auskommentieren
4. Sonderfälle testen: leer, `0`, Umlaute, Gross/Klein (`"anna"` statt `"Anna"`)
5. `print()` mit Label: `print("x ist:", x, type(x))`
6. Ruhig beobachten, nicht hektisch ändern

- **Rubber Duck Debugging:** Code laut einer Gummiente erklären
- In Schleifen nur gefiltert ausgeben (`if i % 10 == 0`)
- Danach Debug-Prints **wieder löschen**

---

## Debugger in PyCharm

1. **Breakpoint:** auf die Zeilennummer klicken (roter Punkt)
2. **Debug** starten (Käfer oben rechts)
3. Variablen mit Wert und Typ live beobachten, aktuelle Zeile ist markiert

| Aktion | Taste | Wirkung |
|--------|-------|---------|
| Step Over | `F8` | Zeile ausführen, Funktion als eine Zeile |
| Step Into | `F7` | in die Funktion hineinspringen |
| Resume | `F9` | bis zum nächsten Breakpoint |

---

→ [[17 - Probleme lösen]] · [[19 - Entwickler-Tests]] · [[01 - Python und IDE]]
