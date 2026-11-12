# Entwickler-Tests

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #Testing #assert #Testprotokoll

---

## Wozu testen?

Ein Test prüft, ob der Code tut, was er soll: Werte rein, Ergebnis kontrollieren. Das spart Zeit, gibt Sicherheit und hilft beim Lernen.

- **Entwicklertest** = kleiner Test, den ich selber für meinen Code schreibe
- **manuell** (starten, eingeben, prüfen) oder **automatisch**
- Für meinen Code bin ich **selber verantwortlich**. Tests von QA und Kunden ersetzen das nicht.
- Je früher ich einen Fehler finde, desto einfacher ist er zu beheben.

---

## Unittests mit assert

Ein Unittest prüft **eine** Funktion. Stimmt der Vergleich, passiert nichts, sonst gibt es einen `AssertionError`.

```python
def verdoppeln(x):
    return x * 2

assert verdoppeln(3) == 6
assert verdoppeln(0) == 0
assert verdoppeln(-2) == -4
```

**Was testen?**

| Art | Beispiel |
|-----|----------|
| Normalfälle | typische Eingaben |
| Sonderfälle | `0`, leerer String, grosse Zahlen |
| Falsche Eingaben | Ungültiges vom Benutzer |

Am Anfang im selben File, später in `test_meinprogramm.py`. Ein Test prüft **eine Sache**, lieber mehrere kleine.

**Typische Fehler:** falsche Resultate, Abstürze bei nicht bedachten Eingaben, unerwartetes Verhalten.

---

## Testarten

| Testart | Prüft |
|---------|-------|
| **Unittest** | einzelne Funktion |
| **Integrationstest** | Zusammenspiel (z. B. Code + Datenbank) |
| **Blackbox** | Verhalten von aussen, Innenleben egal |
| **Whitebox** | Aufbau von innen, alle Fälle und Abzweigungen |

---

## Testprotokoll

Hält fest, **was getestet wurde, was passieren sollte und was passiert ist.** Form ist frei (Tabelle, Liste, Kommentar im Code).

| Testfall | Eingabe | Erwartet | Ergebnis |
|----------|---------|----------|----------|
| verdoppeln(3) | 3 | 6 | erfolgreich |
| verdoppeln("Hallo") | "Hallo" | "HalloHallo" | erfolgreich |
| verdoppeln(None) | None | TypeError | erfolgreich |
| Login falsches Passwort | "Max", falsch | Fehlermeldung | fehlgeschlagen, Bug melden |

---

→ [[18 - Debugging]] · [[14 - Eigene Funktionen]] · [[17 - Probleme lösen]]
