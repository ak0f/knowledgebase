# Python und IDE

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #IDE #PyCharm

---

## Was ist eine IDE?

**IDE** = Integrated Development Environment. Damit schreibe, starte und teste ich Code an einem Ort.

- Syntaxfarben, Autovervollständigung, Fehler direkt beim Schreiben
- Debugger, Projektverwaltung, Git integriert
- Wir nutzen **PyCharm** (JetBrains). Andere: VSCode, IntelliJ, Eclipse

---

## Installation

1. **Python** von `python.org/downloads`, Installer starten, **Add python.exe to PATH** anwählen, Install Now
2. **JetBrains Account** mit Bbc-Mail, Studentenlizenz anfordern (gratis im Basislehrjahr)
3. **Toolbox** installieren, einloggen, **PyCharm** installieren

![[python-installer.png]]

---

## Erstes Projekt

New Project → Pure Python → Name → Create. Dann Rechtsklick → New → Python File.

```python
print("Hello, World!")
```

Starten mit dem grünen Play-Button oder Rechtsklick → Run.

![[pycharm-new-project.png]]

![[pycharm-oberflaeche.png]]

- **Projektstruktur** links, **Editor** in der Mitte, **Terminal** unten, **Run/Debug** oben rechts
- Rote Wellenlinie = Fehler, gelb = Warnung
- `.venv` = virtuelle Umgebung für Bibliotheken

---

## Begriffe

| Begriff | Bedeutung |
|---------|-----------|
| Debuggen | Fehler (Bugs) suchen und beheben |
| Syntaxfehler | Fehler im Aufbau (z. B. Klammer fehlt) |
| Quellcode | der geschriebene Code |
| Projektstruktur | Ordner und Dateien eines Projekts |

---

## Shortcuts (Windows)

| Aktion | Shortcut |
|--------|----------|
| Überall suchen | `Doppel-Shift` |
| Zeile duplizieren / löschen | `Strg + D` / `Strg + Y` |
| Zeile kommentieren | `Strg + /` |
| Code formatieren | `Strg + Alt + L` |
| Umbenennen | `Shift + F6` |
| Schnelle Korrektur | `Alt + Enter` |
| Ausführen / Debuggen | `Shift + F10` / `Shift + F9` |
| Breakpoint | `Strg + F8` |
| Step Over / Into | `F8` / `F7` |
| Suchen / Ersetzen | `Strg + F` / `Strg + R` |

Themes: *Settings → Appearance → Theme* (z. B. Darcula). Plugins: *Settings → Plugins*.

---

→ [[02 - Variablen und Datentypen]] · [[18 - Debugging]] · [[00 - MOC]]
