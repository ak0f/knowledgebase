# Debugging

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Debugging #Fehler #PyCharm #Breakpoint

---

## Lernziele

- [ ] Die 3 Fehlerarten unterscheiden
- [ ] Die häufigsten Fehlermeldungen verstehen
- [ ] Grenzwerte testen
- [ ] Systematisch Fehler finden
- [ ] Den PyCharm-Debugger bedienen

---

## Was ist Debugging?

**Fehler im Code finden und beheben.** Fast jedes Programm hat Bugs, auch bei Profis. Entscheidend ist, wie man damit umgeht.

### Drei Arten von Fehlern

| Art | Beschreibung | Beispiel |
|-----|--------------|----------|
| **Syntaxfehler** | Code falsch geschrieben, Python kann ihn nicht ausführen | `print("Hallo"` → `SyntaxError` |
| **Laufzeitfehler** | Code ist korrekt, aber beim Ausführen passiert etwas Falsches | `x = 10 / 0` → `ZeroDivisionError` |
| **Logikfehler** | Code läuft ohne Fehler, tut aber das Falsche | `if zahl > 10: print("Zahl ist kleiner")` |

---

## Häufige Fehlermeldungen

| Fehler | Bedeutung | Beispiel |
|--------|-----------|----------|
| `SyntaxError` | Struktur stimmt nicht (Klammer, Anführungszeichen, `=` statt `==`) | `print("Hallo"` |
| `IndentationError` | falsche Einrückung (immer 4 Leerzeichen) | `if True:` ohne eingerückte Zeile |
| `NameError` | Variable existiert nicht (nicht definiert, Tippfehler) | `print(name)` |
| `TypeError` | Typen passen nicht zusammen | `"Zahl:" + 5` |
| `ValueError` | Typ ok, Inhalt falsch | `int("Hallo")` |
| `IndexError` | Index ausserhalb der Liste | `[1, 2, 3][5]` |
| `KeyError` | Schlüssel nicht im Dictionary | `{"name": "Lara"}["alter"]` |
| `ZeroDivisionError` | Division durch 0 | `10 / 0` |

### Wie damit umgehen?

1. **Fehlermeldung von unten nach oben lesen:** unten die Fehlerart, darüber der Ort
2. **In kleinen Schritten testen**, nicht erst nach vielen Zeilen
3. Wenn man nicht weiterkommt: Meldung laut vorlesen, Debugging-Tools nutzen, Code jemandem erklären, fragen: *"Was sollte passieren? Was passiert wirklich?"*

---

## Grenzwerte

Grenzwerte = Zahlen an den **Übergängen** zwischen erlaubten und verbotenen Bereichen. Hier passieren Leichtsinnsfehler (`<` statt `<=`).

**Beispiel:** Schulnote 1 bis 6 → testen: **0, 1** (untere Grenze) und **6, 7** (obere Grenze).

```python
noten_texte = ["Sehr gut", "Gut", "Befriedigend", "Ausreichend", "Mangelhaft", "Ungenügend"]
eingabe = 7

if eingabe < 1 or eingabe > 6:
    print("Fehler: Bitte nur eine Note von 1 bis 6 eingeben.")
else:
    print(f"Deine Note bedeutet: {noten_texte[eingabe - 1]}")
```

Ohne die Prüfung: `7 - 1 = 6` → Index 6 existiert nicht → `IndexError`.

---

## Systematisch Fehler finden

| Schritt | Vorgehen |
|---------|----------|
| 1 | **Was sollte passieren?** Ziel klar aufschreiben |
| 2 | **Wo fängt das Problem an?** Programm in Abschnitte teilen, Zwischenwerte mit `print()` prüfen |
| 3 | **Eingrenzen:** unwichtige Teile auskommentieren |
| 4 | **Sonderfälle testen:** leere Eingabe, `0`, Umlaute, Gross-/Kleinschreibung (`"anna"` statt `"Anna"`) |
| 5 | **print() strategisch:** mit Label und evtl. Typ |
| 6 | **Beobachten statt hektisch ändern:** wie ein Detektiv |

```python
x = 5
print(x)              # schlecht
print("x ist:", x)    # besser
print("Typ von x:", type(x))
```

- **Rubber Duck Debugging:** Code laut einer Gummiente (oder dem Nachbarn) erklären, oft merkt man den Fehler selbst
- Vorsicht bei Schleifen: `if i % 10 == 0: print(i)` statt 1000 Ausgaben
- **Nach dem Debuggen aufräumen:** Debug-Prints wieder löschen

---

## Debugging mit PyCharm

Der **Debugger** zeigt, welche Zeile läuft, welche Werte Variablen haben und wo der Code falsch läuft.

1. **Breakpoint setzen:** links auf die Zeilennummer klicken (roter Punkt)
2. **Debug starten:** Käfer-Symbol oben rechts
3. **Variablen live beobachten:** Wert und Typ, aktuelle Zeile farbig markiert, Call Stack
4. **Schrittweise weitergehen**

| Aktion | Taste | Wirkung |
|--------|-------|---------|
| **Step Over** | `F8` | aktuelle Zeile ausführen, Funktionen als eine Zeile |
| **Step Into** | `F7` | in Funktionsaufruf hineinspringen |
| **Resume** | `F9` | bis zum nächsten Breakpoint weiterlaufen |

Beispiel-Bug: Durchschnitt aus `[-1, -5, 0]` nur über positive Zahlen → `count` bleibt 0 → `ZeroDivisionError`.

---

## Verknüpfungen

→ [[17 - Probleme lösen]]
→ [[19 - Entwickler-Tests]]
→ [[01 - Python und IDE]]
