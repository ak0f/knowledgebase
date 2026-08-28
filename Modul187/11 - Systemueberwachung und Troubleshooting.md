# Systemüberwachung und Troubleshooting

**Modul:** Systemüberwachung und Troubleshooting (100)
**Tags:** #Monitoring #Troubleshooting #TaskManager #htop #Logs

---

## Lernziele

- [ ] Systemressourcen überwachen (CPU, RAM, Festplatte)
- [ ] Prozesse anzeigen und beenden
- [ ] Ereignisprotokolle / Logs auslesen
- [ ] Fehler systematisch eingrenzen (5-Schritte-Methode)

---

## Warum Systemüberwachung?

- Probleme **frühzeitig erkennen** (bevor der PC abstürzt)
- **Ursachen** von Fehlern finden (Was verbraucht so viel RAM?)
- **Performance** optimieren (Welche Programme bremsen?)
- **Sicherheitsvorfälle** entdecken (Unbekannte Prozesse?)

---

## Die wichtigsten Ressourcen

| Ressource | Was ist das? | Problem bei Überlastung |
|-----------|-------------|------------------------|
| **CPU** | Prozessor – "Gehirn" des PCs | System reagiert langsam |
| **RAM** | Arbeitsspeicher | Programme stürzen ab |
| **Festplatte** | Speicherplatz | Keine Updates/Speicherung möglich |
| **Netzwerk** | Datenübertragung | Langsames Internet |

---

## Übersicht der Werkzeuge

| Aufgabe | Windows | Linux |
|---------|---------|-------|
| Prozesse & Ressourcen | Task-Manager | `top` / `htop` |
| Detaillierte Überwachung | Ressourcenmonitor | `htop` / `glances` |
| Ereignisse / Logs | Ereignisanzeige | `journalctl` / `/var/log` |
| Systeminformationen | `msinfo32` | `uname`, `lscpu`, `free` |

---

## Windows – Task-Manager

**Öffnen (3 Wege):**
- `Ctrl + Shift + Esc`
- Rechtsklick auf Taskleiste → Task-Manager
- `Ctrl + Alt + Delete` → Task-Manager auswählen

**Tabs:**

| Tab | Zeigt an |
|-----|---------|
| **Prozesse** | Laufende Programme und Ressourcenverbrauch |
| **Leistung** | CPU, RAM, Datenträger, Netzwerk als Graphen |
| **App-Verlauf** | Ressourcenverbrauch über Zeit |
| **Autostart** | Programme, die beim Start laden |
| **Benutzer** | Wer ist angemeldet? |
| **Details** | Alle Prozesse mit PID |
| **Dienste** | Hintergrunddienste des Systems |

**Prozess beenden:**
- Prozess auswählen → "Task beenden" klicken
- **Achtung: Systemprozesse NIE beenden!**

---

## Windows – Ereignisanzeige

**Öffnen:** `Win + R` → `eventvwr.msc`

**Ereignistypen:**
- Information (normal)
- Warnung (potenzielles Problem)
- Fehler (etwas ist schiefgelaufen)

| Protokoll | Inhalt |
|-----------|--------|
| **System** | Hardware, Treiber, Dienste |
| **Anwendung** | Programmfehler und -meldungen |
| **Sicherheit** | Anmeldeversuche, Rechteverletzungen |

---

## Linux – top und htop

```bash
top       # Standard, überall vorhanden
htop      # Benutzerfreundlicher
```

**Navigation in htop:**
- Pfeiltasten: Prozess auswählen
- `F9`: Prozess beenden (kill)
- `F10` oder `q`: Beenden

**Wichtige Anzeigen:**

| Anzeige | Bedeutung |
|---------|-----------|
| Load Average | Systemlast (1, 5, 15 Min) |
| Tasks | Anzahl laufender Prozesse |
| %CPU | CPU-Auslastung |
| %MEM | RAM-Auslastung |

**Spalten der Prozessliste:**

| Spalte | Bedeutung |
|--------|-----------|
| PID | Prozess-ID (eindeutige Nummer) |
| USER | Besitzer des Prozesses |
| %CPU | CPU-Verbrauch des Prozesses |
| %MEM | RAM-Verbrauch des Prozesses |
| COMMAND | Name des Programms |

---

## Linux – Prozesse beenden

```bash
kill PID              # Prozess "freundlich" beenden
kill -9 PID           # Prozess sofort beenden (erzwingen)
killall programmname  # Prozess nach Namen beenden
```

---

## Linux – Logs anzeigen

```bash
journalctl              # Alle Logs anzeigen
journalctl -p err       # Nur Fehler anzeigen
journalctl -f           # Live-Ansicht (neue Einträge)
journalctl -b           # Logs seit dem letzten Boot
```

**Klassische Log-Dateien:**
- `/var/log/syslog` – Systemmeldungen
- `/var/log/auth.log` – Anmeldeversuche

---

## Systematische Fehlereingrenzung – 5-Schritte-Methode

1. **Problem beschreiben** – Was genau? Seit wann?
2. **Kategorie bestimmen** – Hardware? Software? Netzwerk?
3. **Informationen sammeln** – Logs und Ressourcen prüfen
4. **Hypothese testen** – Eine Änderung nach der anderen!
5. **Dokumentieren** – Problem und Lösung festhalten

---

## Typische Fehlerquellen

| Symptom | Mögliche Ursache | Prüfen mit |
|---------|-----------------|------------|
| PC sehr langsam | CPU 100% | Task-Manager / htop |
| Programme stürzen ab | RAM voll | Task-Manager / `free -h` |
| "Speicher voll" | Festplatte voll | Explorer / `df -h` |
| Kein Internet | Netzwerkproblem | ping, Logs |

---

## Merksatz

> Die Konzepte sind gleich – nur die Werkzeuge unterscheiden sich!
> Windows: Task-Manager / Ereignisanzeige
> Linux: htop / journalctl

---

## Verknüpfungen

→ [[10 - Bootvorgang und BIOS-UEFI]]
→ [[03 - Linux Kennenlernen]]
→ [[Befehle-Cheatsheet]]
