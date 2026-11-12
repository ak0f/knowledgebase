# Entwickler-Tests

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Testing #Unittest #assert #Testprotokoll

---

## Lernziele

- [ ] Erklären, was ein Test und ein Entwicklertest ist
- [ ] Einfache Unittests mit `assert` schreiben
- [ ] Testarten unterscheiden (Unit, Integration, Blackbox, Whitebox)
- [ ] Ein Testprotokoll führen

---

## Was ist ein Test?

Ein kontrollierter Ablauf, der prüft, ob der Code tut, was er soll: Werte eingeben, Ergebnis kontrollieren.

**Warum testen?**

- spart Zeit bei Änderungen
- gibt Sicherheit
- hilft beim Lernen

**Entwicklertests** = kleine, gezielte Tests, die man **selbst** schreibt:

- liefert die Funktion mit verschiedenen Eingaben das richtige Resultat?
- werden spezielle/ungültige Eingaben richtig behandelt?
- läuft der Code nach Änderungen noch korrekt?

**Manuell** (Programm starten, eingeben, Resultat prüfen) oder **automatisch** (kleine Programme, die den Code testen).

> Je früher ein Fehler gefunden wird, desto einfacher ist er zu beheben.

### Verantwortung

- Für den eigenen Code ist man **selbst verantwortlich**
- Tests von QA und Kund:innen **ersetzen** die eigenen Tests nicht
- Gut testbarer Code ist meist auch **besser strukturiert**

---

## Einfache Unittests

Ein **Unittest** ist ein kleiner automatisierter Test für **eine** Funktion. Ergebnis wird mit dem erwarteten Wert verglichen, z. B. mit `assert`.

```python
def verdoppeln(x):
    return x * 2

assert verdoppeln(3) == 6      # stimmt: nichts passiert
assert verdoppeln(0) == 0
assert verdoppeln(-2) == -4
assert verdoppeln(2) == 5      # AssertionError: Test fehlgeschlagen
```

**Was testen?**

| Art | Beispiel |
|-----|----------|
| Normale Fälle | typische Eingaben |
| Besondere Fälle | `0`, leerer String, sehr grosse Zahlen |
| Falsche Eingaben | Ungültiges vom Benutzer |

- Am Anfang im selben File, später eigene Datei, z. B. `test_meinprogramm.py`
- Ein Test prüft **genau eine Sache**, lieber viele kleine als ein grosser

**Übung:** eigene Funktion testen mit zwei positiven Zahlen, einer negativen Zahl und einer Null.

---

## Fehler früh finden

Typische Fehler:

- **Falsche Resultate** (Funktion läuft, Ergebnis stimmt nicht)
- **Abstürze** (nicht bedachte Eingabe)
- **Unerwartetes Verhalten**

Beispiel: Rabatt-Funktion mit 100, 50 und 0 Franken testen.

> Fehler zu machen ist normal. Sie rechtzeitig zu erkennen ist gute Arbeitsweise.

---

## Testarten

| Testart | Prüft | Merkmal |
|---------|-------|---------|
| **Unittest** | einzelne Funktion/Methode | klein, schnell, von Entwickler:innen |
| **Integrationstest** | Zusammenspiel (z. B. Code + Datenbank/Webserver) | funktionieren die Teile zusammen? |
| **Blackbox-Test** | Verhalten von aussen | Innenleben egal, nur Ein- und Ausgabe |
| **Whitebox-Test** | Aufbau von innen | Code bekannt, alle Fälle/Abzweigungen abdecken |

---

## Testprotokoll

Hält fest: **Was wurde getestet? Was sollte passieren? Was ist passiert?** Optional Umgebung (Betriebssystem, Browser) und offene Punkte.

| Testfall | Eingabe / Aktion | Erwartetes Ergebnis | Ergebnis | Kommentar |
|----------|------------------|---------------------|----------|-----------|
| verdoppeln(3) | 3 | 6 | erfolgreich | |
| verdoppeln("Hallo") | "Hallo" | "HalloHallo" | erfolgreich | Strings werden auch verdoppelt |
| verdoppeln(None) | None | Fehler (TypeError) | erfolgreich | Fehler wie erwartet |
| Login mit leerem Passwort | Formular absenden | Fehlermeldung | erfolgreich | Validierung funktioniert |
| Login mit falschem Passwort | "Max", falsches PW | Fehlermeldung | fehlgeschlagen | Bug melden |

- Form frei: Tabelle, Liste oder Kommentar im Code
- Im Team absprechen, welche Infos wichtig sind

---

## Verknüpfungen

→ [[18 - Debugging]]
→ [[14 - Eigene Funktionen]]
→ [[17 - Probleme lösen]]
