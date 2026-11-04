# 14 – Defekte und Konfigurationsfehler beheben

> **Handlungsziel 4:** ICT-Arbeitsplatz testen, Defekte und Konfigurationsfehler systematisch eingrenzen und beheben.

---

## Lernziele

- [ ] 4.1 Wichtigste Kategorien von Fehlermeldungen kennen (Hardware, Betriebssystem, Anwendungen)
- [ ] 4.2 Methode der systematischen Eingrenzung (Ausschlussverfahren) anwenden können
- [ ] Hilfreiche Diagnosetools kennen und einsetzen können
- [ ] Ablaufdiagramm (Flussdiagramm) zur Fehlerbehebung erstellen können

---

## Fehlerkategorien

| Kategorie | Beispiele |
|-----------|-----------|
| **Hardware** | PC startet nicht, kein Bild, Gerät nicht erkannt, Bluescreen |
| **Betriebssystem** | BSOD (Bluescreen), Boot-Fehler, fehlende Treiber |
| **Anwenderprogramme** | Programm startet nicht, Datei öffnet mit falschem Programm |
| **Peripherie** | Drucker funktioniert nicht, kein Zugriff auf USB-Gerät |
| **Netzwerk** | Kein Internet, IP-Konflikt, DNS-Fehler |

---

## Systematisches Vorgehen (Ausschlussverfahren)

1. **Fehler lesen** – Fehlermeldung genau verstehen
2. **Vom Allgemeinen ins Detail** – Grobes Problem eingrenzen
3. **Ausschlussverfahren** – Funktionierende Teilsysteme ausschliessen

**Beispiel: "Kein Bild auf dem Monitor"**
```
Monitor ein? → Kabel korrekt? → Richtige Eingangsquelle? → Monitor-Test → Grafikkarte? → PC-Start?
```

**Ablaufdiagramm erstellen:** https://draw.io (New → Flowchart)

---

## Flussdiagramm-Symbole (Standard)

| Symbol | Bedeutung |
|--------|-----------|
| Oval / Abgerundetes Rechteck | Start / Ende |
| Rechteck | Prozess / Aktion |
| Raute | Entscheidung (Ja/Nein) |
| Pfeil | Flussrichtung |
| Parallelogramm | Ein-/Ausgabe |

---

## Diagnosetools Windows

| Tool | Befehl | Zweck |
|------|--------|-------|
| **Ereignisanzeige** | `eventvwr.exe` | System-Logs, Fehler und Warnungen |
| **Taskmanager** | `taskmgr.exe` | Ressourcen, laufende Prozesse |
| **Ressourcenmonitor** | `resmon.exe` | Detaillierte Ressourcen-Analyse |
| **Leistungsmonitor** | `perfmon.exe` | Langzeit-Performance-Monitoring |
| **Gerätemanager** | `devmgmt.msc` | Hardware-Status, Treiber-Probleme |
| **Systeminformation** | `msinfo32` | Vollständige Hardware-/Software-Übersicht |
| **Datenträgerverwaltung** | `diskmgmt.msc` | Disk-Status, Partitionen |
| **Netzwerkdiagnose** | `ipconfig`, `ping`, `tracert` | Netzwerk-Verbindungsprobleme |

---

## Typische Fehler und Lösungsansätze

| Problem | Erste Schritte |
|---------|---------------|
| **Bluescreen (BSOD)** | Ereignisanzeige prüfen, Treiber aktualisieren, RAM testen |
| **PC bootet nicht** | BIOS-Einstellungen, Boot-Reihenfolge, Kabel prüfen |
| **Kein Bild** | Kabel, Eingabe-Quelle, Monitor an anderem PC testen |
| **Kein Internet** | `ipconfig /all`, `ping 8.8.8.8`, DNS, Gateway prüfen |
| **Langsamer PC** | Taskmanager (Autostart), Datenträger, RAM prüfen |
| **Drucker druckt nicht** | Druckerwarteschlange, Treiber, Verbindung prüfen |
| **Gerät nicht erkannt** | Gerätemanager, Treiber (neu-)installieren |

---

## Flaschenhals (Bottleneck) finden

**Engpass-Analyse:**
- **CPU-Auslastung:** Taskmanager / `top`
- **RAM-Auslastung:** Taskmanager / `free -h`
- **Disk-Auslastung:** Ressourcenmonitor / `df -h`, `iostat`
- **Netzwerk:** Ressourcenmonitor / Netzwerk-Tab

> Frage: Erbringt meine Hardware noch die geforderte Leistung?

---

## Verknüpfungen

→ [[13 - Ressourcen und Ereignisse überwachen]]
→ [[05 - Netzzugang einrichten]]
→ [[Befehle-Cheatsheet]]
→ [[00 - MOC]]
