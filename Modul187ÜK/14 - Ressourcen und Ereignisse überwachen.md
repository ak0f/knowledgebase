# 13 – Ressourcen und Ereignisse überwachen

> **Handlungsziel 9:** Ressourcen und Ereignisse überwachen. Im Betriebssystem enthaltene Hilfsprogramme zur Problemanalyse und -behebung einsetzen.

---

## Lernziele

- [ ] 9.1 Werkzeuge zur Systemüberwachung kennen (Taskmanager, Ereignisanzeige, Gerätemanager, Systeminformation, Protokolldateien)
- [ ] 9.2 Werkzeuge zur Beeinflussung von Ressourcen kennen (CPU, RAM, Auslagerungsspeicher, Datenträgerbelegung)
- [ ] Äquivalente Linux-Tools kennen (top, nice, kill)

---

## Was sind Ressourcen?

- **Allgemein:** Verfügbare Mittel
- **Computer-spezifisch:**
  - CPU (Leistung / Zeit)
  - RAM (Grösse)
  - Festplatte / SSD (Grösse, I/O)
  - Netzwerk-Bandbreite
  - (Dienste, Daten)

**Warum überwachen?**
- Ressourcen sind **immer endlich**
- Engpässe früh erkennen (bevor nichts mehr geht)
- Sicherheit: Auditing und Accounting

---

## Windows-Tools zur Ressourcenüberwachung

| Tool | Befehl | Zweck |
|------|--------|-------|
| **Taskmanager** | `taskmgr.exe` / Strg+Shift+Esc | Laufende Tasks + aktueller Ressourcenverbrauch |
| **Ressourcenmonitor** | `resmon.exe` | Detaillierte Ressourcenansicht (CPU, RAM, Disk, Netz) |
| **Leistungsmonitor** | `perfmon.exe` | Langzeit-Monitoring, Graphen, Datensammler |
| **Ereignisanzeige** | `eventvwr.exe` | System- und Anwendungs-Logs |
| **Gerätemanager** | `devmgmt.msc` | Alle erkannte Hardware + Treiber-Status |
| **Systeminformation** | `msinfo32` | Vollständige Systemübersicht |
| **Explorer** | – | Datenträgerbelegung im Dateisystem |
| **Datenträgerverwaltung** | `diskmgmt.msc` | Partitionen + Volume-Belegung |

---

## Ereignisanzeige (Event Viewer)

- System und Anwendungen schreiben ihre Meldungen hier
- **Prioritäten beachten:**
  - ❌ **Kritisch** → sofort handeln
  - ❌ **Fehler** → untersuchen
  - ⚠️ **Warnung** → beobachten
  - ℹ️ **Information** → normal
- Auditing (Überwachung): Wer hat wann auf was zugegriffen?

---

## Ressourcen beeinflussen (Windows)

| Aktion | Methode |
|--------|---------|
| CPU-Priorität ändern | Taskmanager → Details → Rechtsklick → Priorität |
| Autostart deaktivieren | Taskmanager → Autostart ODER `msconfig` |
| Software deinstallieren | Einstellungen → Apps |
| Quota (Speicherlimit) | Datenträgerverwaltung → Quoten |

> Prioritäten ändern = sehr selten sinnvoll/notwendig!

---

## Linux-Tools zur Ressourcenüberwachung

| Befehl | Funktion |
|--------|---------|
| `top` | Aktuelle Prozesse + CPU/RAM-Verbrauch (Echtzeit, `q` zum Beenden) |
| `htop` | Verbessertes `top` (falls installiert) |
| `df -h` | Datenträgerbelegung (human-readable) |
| `free -h` | RAM-Verbrauch anzeigen |
| `ps aux` | Alle laufenden Prozesse |

---

## Ressourcen beeinflussen (Linux)

```bash
# Priorität ändern (CPU): -20 (höchste) bis 19 (niedrigste)
nice -n -10 ping 8.8.8.8      # Neuen Prozess mit höherer Priorität starten

# Prozess beenden
kill -9 PID                    # Hard Kill (sofort, unüberspringbar)
kill PID                       # Normaler Kill (graceful)
killall firefox                # Alle Prozesse mit diesem Namen beenden
```

---

## Monitoring grosser Infrastrukturen

- **Agent** auf jedem Server **oder** SNMP-Protokoll
- Zentrale Sammlung von: Dienste-Zustand, Ressourcen, Logdateien
- Beispiele: **PRTG**, **Nagios**, Zabbix, Prometheus

---

## Verknüpfungen

→ [[12 - Sicheres Arbeiten als Administrator]]
→ [[14 - Defekte und Konfigurationsfehler beheben]]
→ [[Befehle-Cheatsheet]]
→ [[00 - MOC]]
