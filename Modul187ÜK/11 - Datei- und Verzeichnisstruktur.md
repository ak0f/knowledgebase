# 10 – Datei- und Verzeichnisstruktur

> **Handlungsziel 8.2/8.3:** Konzepte für Verzeichnishierarchien und Zugriff auf Datenträger kennen.

---

## Lernziele

- [ ] 8.2 Verzeichnishierarchien verstehen (absolute/relative Pfade, Links, versteckte Dateien)
- [ ] 8.3 Zugriff auf Datenträger und Dateisysteme verstehen (Mount, Devicedateien, Treiber)
- [ ] Standardverzeichnisse unter Windows kennen
- [ ] Standardverzeichnisse unter Linux kennen (FHS)
- [ ] Navigationsbefehle Windows und Linux anwenden können

---

## Datenträger: Windows vs. Linux

| | Windows | Linux |
|--|---------|-------|
| Adressierung | Laufwerksbuchstaben (C:, D:...) | Mountpoints (/mnt, /boot...) |
| Struktur | Alle Laufwerke auf gleicher Ebene | Eine einzige Verzeichnishierarchie |
| Hauptlaufwerk | C:\ | / (root) |
| Einbinden | Automatisch / Datenträgerverwaltung | `mount`-Befehl |

---

## Standardverzeichnisse Windows

| Pfad | Bedeutung |
|------|-----------|
| `C:\` | Hauptlaufwerk, oberster Ordner |
| `C:\Windows` | Windows-Hauptordner |
| `C:\Windows\System32` | Systemprogramme (64-Bit) |
| `C:\Windows\SysWOW64` | 32-Bit-Hilfsprogramme unter 64-Bit-Windows |
| `C:\Windows\Fonts` | Schriftarten |
| `C:\Windows\Logs` | Logs weiterer Dienste |
| `C:\Windows\WinSxS` | Ältere Versionen von aktualisierten Produkten (nicht manuell löschen!) |
| `C:\Program Files` | Programme (64-Bit) |
| `C:\Program Files (x86)` | Programme (32-Bit) |
| `C:\Users` | Benutzerprofile |
| `C:\ProgramData` | Anwendungseinstellungen (versteckt, keine Admin-Rechte nötig) |

**Treiber-Pfade:**
- `C:\Windows\System32\DriverStore`
- `C:\Windows\System32\Drivers`
- `C:\Windows\inf`

---

## Standardverzeichnisse Linux (FHS – Filesystem Hierarchy Standard)

| Pfad | Bedeutung |
|------|-----------|
| `/` | Oberster Ordner (root folder) |
| `/bin` | Binärdateien (Tools, Programme) |
| `/boot` | Boot-Dateien (inkl. Linux-Kernel) |
| `/dev` | Gerätedateien (Devices) |
| `/etc` | Konfigurationsdateien (editierbar) |
| `/home` | Heimverzeichnisse der Benutzer |
| `/lib` | Bibliotheken |
| `/mnt` | Mountpoints (temporär) |
| `/opt` | Optionale (Dritt-)Software |
| `/proc` | Informationen über laufende Prozesse |
| `/root` | Heimverzeichnis des root-Benutzers |
| `/sbin` | Systemprogramme (nur root/sudo) |
| `/tmp` | Temporäres Verzeichnis (für alle Benutzer) |
| `/usr` | Weitere Tools (nicht direkt zum System) |
| `/var` | Variable Dateien (Logs, Webseiten) |

---

## Absolute vs. Relative Pfade

| | Absoluter Pfad | Relativer Pfad |
|--|---------------|----------------|
| **Definition** | Immer vom Wurzel-Verzeichnis (/ oder C:\) | Relativ zum aktuellen Verzeichnis |
| **Linux-Beispiel** | `/home/tux/datei.txt` | `../log/auth.log` |
| **Windows-Beispiel** | `C:\Windows\file.txt` | `..\file.txt` |

**Sonderpfade:**
- `.` = aktuelles Verzeichnis
- `..` = ein Verzeichnis nach oben
- `~` = Heimverzeichnis des Benutzers (Linux)

---

## Navigationsbefehle

### Linux (Terminal)

```bash
pwd                     # Aktuelles Verzeichnis anzeigen (path of current working directory)
cd /home/user1          # Absoluter Pfad: Wechsel zu /home/user1
cd user1                # Relativer Pfad: Wechsel in Unterordner "user1"
cd ..                   # Ein Verzeichnis nach oben
cd ~                    # Ins Heimverzeichnis
ls -la                  # Verzeichnisinhalt (inkl. versteckte Dateien)
ls -l datei.txt         # Datei-Details inkl. Berechtigungen anzeigen
```

### Windows (CMD/PowerShell)

```powershell
cd C:\Windows           # Wechsel zu absoluten Pfad
cd ..                   # Ein Verzeichnis nach oben
dir                     # Verzeichnisinhalt anzeigen
dir /a                  # Inkl. versteckte Dateien
```

---

## Versteckte Dateien

- **Windows:** Dateien/Ordner mit Punkt vorn NICHT versteckt; Attribut "versteckt" → `dir /a`
- **Linux:** Dateien/Ordner die mit `.` beginnen sind versteckt → `ls -a`

---

## Verknüpfungen

→ [[09 - Datenträger Partitionen und Dateisysteme]]
→ [[11 - Benutzer und Gruppen]]
→ [[00 - MOC]]
