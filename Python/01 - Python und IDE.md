# Python und IDE

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #IDE #PyCharm #Installation

---

## Lernziele

- [ ] Erklären, was eine IDE ist und wozu man sie braucht
- [ ] Python, JetBrains Toolbox und PyCharm installieren
- [ ] Ein Projekt anlegen und "Hello, World!" ausführen
- [ ] Wichtige Funktionen und Shortcuts von PyCharm kennen

---

## Was ist eine IDE?

**IDE = Integrated Development Environment** (Integrierte Entwicklungsumgebung).
Ein Werkzeug, mit dem man Code effizient schreibt, ausführt und testet.

**Warum eine IDE?**

- **Syntaxhervorhebung** – Befehle, Variablen usw. haben verschiedene Farben
- **Autovervollständigung** – spart Tipparbeit, verhindert Fehler
- **Fehlermeldungen in Echtzeit** – schon beim Schreiben
- **Debugger** – Programme gezielt testen
- **Projektverwaltung** – Struktur für Dateien und Ordner
- **Integration von Tools** – z. B. Git, Datenbanken, Testsysteme

| Sprache | Beispiele für IDEs |
|---------|--------------------|
| Python | PyCharm, VSCode |
| Java | IntelliJ IDEA, Eclipse |
| C/C++ | CLion, Visual Studio |
| Web (HTML/CSS/JS) | VSCode, WebStorm |

Wir verwenden **PyCharm** von JetBrains.

---

## Installation

### 1. Python installieren

1. Download auf `python.org/downloads` (offizieller Installer)
2. Admin-Rechte sicherstellen
3. Installer starten, **Install Now** klicken
4. **Add python.exe to PATH** anwählen (wichtig!)

![[python-installer.png]]

### 2. JetBrains Account

- Account mit der **Bbc-Mail** erstellen (`account.jetbrains.com`)
- Studentenlizenz anfordern (`jetbrains.com/community/education`) – während des Basislehrjahrs gratis
- Bestätigungslink kommt an die persönliche Mailadresse

### 3. Toolbox und PyCharm

- JetBrains **Toolbox** installieren, starten, einloggen
- In der Toolbox bei *Available* **PyCharm** suchen und installieren

---

## Erstes Projekt

1. PyCharm starten → **New Project**
2. **Pure Python** wählen, Projektname vergeben
3. Interpreter wählen (sollte schon eingerichtet sein) → **Create**

### Die Oberfläche

![[pycharm-new-project.png]]

![[pycharm-oberflaeche.png]]

- **Projektstruktur (links)** – Dateien und Ordner
- **Editor (Mitte)** – hier schreibst du den Code
- **Terminal (unten)** – Eingaben wie in der Kommandozeile
- **Run/Debug-Buttons (oben rechts)** – ausführen oder testen

### Erstes Programm

Rechtsklick auf Projekt → *New* → *Python File* → Name `main`

```python
print("Hello, World!")
```

Ausführen: Rechtsklick → *Run 'main'* oder grüner Play-Button.

---

## Nützliche Funktionen

| Funktion | Beschreibung |
|----------|--------------|
| Code-Vervollständigung | schlägt beim Tippen Begriffe vor (`pri` → `print()`) |
| Syntax-Hervorhebung | Funktionen blau, Strings grün, Kommentare grau |
| Fehler in Echtzeit | rote Wellenlinie = Fehler, gelb = Warnung |
| Navigation | `Strg + Klick` springt zur Definition |
| Run / Debug | Play-Button = ausführen, Käfer = Schritt für Schritt |
| Virtuelle Umgebung | `.venv` im Projekt, wichtig für Bibliotheken |
| Terminal & Git | beides direkt in der IDE |

---

## Wichtige Begriffe

| Begriff | Bedeutung |
|---------|-----------|
| IDE | Software zum Schreiben, Testen und Verbessern von Programmen |
| Programmieren / Coden | Anweisungen für den Computer schreiben |
| Debuggen | Fehler (Bugs) suchen und beheben |
| Projektstruktur | Organisation der Dateien und Ordner |
| Autovervollständigung | IDE schlägt beim Tippen Code vor |
| Syntaxfehler | Fehler im Aufbau, z. B. fehlende Klammer |
| Quellcode | der geschriebene Programmtext |
| Ausgabe | Ergebnis, das das Programm anzeigt |

---

## Keyboard Shortcuts (Windows)

**Navigation**

| Aktion | Shortcut |
|--------|----------|
| Überall suchen | `Doppel-Shift` |
| Zu Klasse gehen | `Strg + N` |
| Zu Datei gehen | `Strg + Shift + N` |
| Letzte Dateien | `Strg + E` |
| Definition anzeigen | `Strg + Klick` / `Strg + B` |

**Code bearbeiten**

| Aktion | Shortcut |
|--------|----------|
| Zeile duplizieren | `Strg + D` |
| Zeile löschen | `Strg + Y` |
| Code formatieren | `Strg + Alt + L` |
| Vervollständigung | `Strg + Leertaste` |
| Zeile verschieben | `Strg + Shift + ↑/↓` |
| Umbenennen | `Shift + F6` |
| Zeile kommentieren | `Strg + /` |
| Schnelle Aktionen | `Alt + Enter` |

**Ausführen und Debuggen**

| Aktion | Shortcut |
|--------|----------|
| Ausführen | `Shift + F10` |
| Debuggen | `Shift + F9` |
| Breakpoint | `Strg + F8` |
| Step Over | `F8` |
| Step Into | `F7` |

**Suchen**

| Aktion | Shortcut |
|--------|----------|
| Suchen | `Strg + F` |
| Ersetzen | `Strg + R` |
| In allen Dateien suchen | `Strg + Shift + F` |

---

## Bonus: Themes und Plugins

- Theme: *File → Settings → Appearance & Behavior → Theme* (z. B. Darcula dunkel)
- Plugins: *File → Settings → Plugins* (z. B. Rainbow Brackets, Key Promoter X)

---

## Verknüpfungen

→ [[02 - Variablen und Datentypen]]
→ [[18 - Debugging]]
→ [[00 - MOC]]
