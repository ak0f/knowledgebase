# Windows Konfiguration

**Modul:** Windows Konfiguration (210)
**Tags:** #Windows #Konfiguration #Desktop #Explorer #Treiber #CloudApps

---

## Lernziele

- [ ] Desktop personalisieren (Hintergrundbild, Startmenü, Taskleiste)
- [ ] Explorer-Einstellungen kennen (Dateiendungen, versteckte Dateien)
- [ ] Standardprogramme definieren
- [ ] Treiber installieren und Gerätemanager nutzen
- [ ] Programme installieren, aktualisieren, deinstallieren
- [ ] Unterschied **Cloud-Apps vs. Desktop-Apps** erklären
- [ ] Systemvariablen und spezielle Dateien kennen (`pagefile.sys`, `hiberfil.sys`)
- [ ] Autostart optimieren (msconfig, Taskmanager, shell:startup)
- [ ] **3 Best Practices** Windows Konfiguration nennen

---

## Desktop anpassen

- Hintergrundbild ändern: Rechtsklick Desktop → Personalisieren
- Startmenü anpassen: Angeheftete Apps verwalten
- Taskleiste anpassen: Symbole ein-/ausblenden

---

## Windows Explorer

| Einstellung | Wo zu finden |
|------------|-------------|
| Dateiendungen anzeigen | Ansicht → Anzeigen → Dateinamenerweiterungen |
| Versteckte Dateien anzeigen | Ansicht → Anzeigen → Ausgeblendete Elemente |
| Ansicht ändern | Ansicht → Layout |

**Wichtige Shortcuts:**

| Shortcut | Funktion |
|---------|---------|
| `Win + E` | Explorer öffnen |
| `Alt + F4` | Programm schliessen |
| `Win + Pfeiltaste` | Fenster verschieben/andocken |

---

## Treiber

> **Treiber** = Software, die Betriebssystem und Hardware verbinden

- Gerätemanager prüfen: `devmgmt.msc`
- Gelbes `!` = fehlender oder fehlerhafter Treiber
- Treiber nachinstallieren: Herstellerwebsite bevorzugen

---

## Programme installieren

- **Standardprogramme** definieren: Einstellungen → Apps → Standard-Apps
- **Windows Funktionen** aktivieren/deaktivieren: Systemsteuerung → Windows-Features
- Programme deinstallieren: Einstellungen → Apps → Installierte Apps

---

## Cloud-Apps vs. Desktop-Apps

| | Cloud-Apps | Desktop-Apps |
|--|-----------|-------------|
| Installation | Oft keine nötig (Webapps) | Lokale Installation |
| Plattform | Plattformunabhängig | Je OS eigene Version |
| Updates | Automatisch (Updatezwang) | Manuell oder automatisch |
| Datenspeicherung | Externe Datenquelle (Cloud) | Lokal |
| Zusammenarbeit | Einfach, auch extern | Eingeschränkter |
| Beispiele | Microsoft 365 Online, Google Docs | Word, Excel lokal |

---

## Microsoft 365 – Lizenzübersicht

| Lizenz | Zielgruppe |
|--------|-----------|
| M365 Family / Personal | Privatanwender |
| M365 Business Basic | KMU bis 300 User |
| M365 Business Standard | KMU |
| M365 Business Premium | KMU mit erweiterten Sicherheitsfunktionen |
| M365 Apps for Enterprise | Grosse Unternehmen |
| M365 E3 / E5 | Enterprise |

---

## Systemvariablen & spezielle Dateien

| Datei / Pfad | Bedeutung |
|-------------|----------|
| `pagefile.sys` | Auslagerungsdatei (virtueller RAM) |
| `hiberfil.sys` | Ruhezustand-Datei |
| `C:\Windows\Installer` | Installationsdateien |
| `C:\Windows\WinSxS` | Side-by-Side Assemblies (kann gross werden) |
| `C:\Windows\System32\driverstore` | Treiberspeicher |
| `%PATH%` | Pfadangabe für CMD (inkl. System32, Programme) |

---

## Speicherknappheit lösen

- Papierkorb leeren
- Download-Ordner aufräumen
- Datenträgerbereinigung: `cleanmgr`

---

## Autostart optimieren

| Methode | Weg |
|--------|-----|
| Taskmanager | Autostart-Tab → Programme deaktivieren |
| msconfig | `msconfig` → Dienste |
| Autostart-Ordner | `shell:startup` in Explorer eingeben |
| Geplante Tasks | Aufgabenplanung (`taskschd.msc`) |

---

## Best Practices Windows Konfiguration

1. Keine unnötigen Programme installieren (regelmässig deinstallieren)
2. Nicht benötigte Dienste / Autostart-Programme deaktivieren
3. Treiber aktuell halten

---

## Verknüpfungen

→ [[02 - Windows Installation und Lizenzen]]
→ [[04 - Windows Unterhalt und Updates]]
→ [[00 - MOC]]
