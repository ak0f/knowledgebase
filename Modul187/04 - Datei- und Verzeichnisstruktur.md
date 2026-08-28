# Datei- und Verzeichnisstruktur

**Modul:** Datei- und Verzeichnisstruktur (210)
**Tags:** #Linux #Windows #Dateisystem #Pfade

---

## Lernziele

- [ ] Absoluten Pfad (beginnt mit `/`) vs. relativen Pfad (`.` und `..`) unterscheiden
- [ ] Linux-Verzeichnisse nennen: `/`, `/bin`, `/etc`, `/home`, `/media`, `/mnt`
- [ ] Windows-Verzeichnisse nennen: `C:\`, `C:\Users\`, `C:\Windows\System32\`, `C:\Program Files\`
- [ ] Mountpoint erklären
- [ ] `sudo mount /dev/sdc1 /mnt` anwenden
- [ ] `df -h` lesen und erklären

---

## Pfadtypen

### Absoluter Pfad
- Beginnt immer vom Root-Verzeichnis
- **Linux:** `/home/tux/datei.txt`
- **Windows:** `C:\Users\tux\datei.txt`

### Relativer Pfad
- Bezieht sich auf das **aktuelle Verzeichnis**
- `.` = aktuelles Verzeichnis
- `..` = übergeordnetes Verzeichnis
- Beispiel: `../../log/auth.log`

---

## Linux Verzeichnisstruktur

```
/                   Root (Wurzel)
├── bin             Systemprogramme (ls, cp, mv...)
├── boot            Bootloader, Kernel
├── dev             Gerätedateien (Hardware)
├── etc             Konfigurationsdateien
├── home            Benutzerverzeichnisse (/home/tux)
├── lib             Systembibliotheken
├── media           CD, USB (automatisch gemountet)
├── mnt             Netzwerk, USB (manuell gemountet)
└── opt             Optionale Software
```

**Wichtige Mountpoints:**

| Pfad | Bedeutung |
|------|-----------|
| `/` | Root – alles beginnt hier |
| `/boot` | Bootdateien |
| `/media` | Wechselmedien (CD/USB, automatisch) |
| `/mnt` | Manueller Mountpunkt |

---

## Windows Verzeichnisstruktur

| Pfad | Inhalt |
|------|--------|
| `C:` | Systemlaufwerk |
| `D:` | Datenlaufwerk |
| `E:` | USB / externes Laufwerk |
| `C:\Users\` | Benutzerprofile |
| `C:\Windows\` | Windows-System |
| `C:\Windows\System32\` | 64-Bit Systemdateien |
| `C:\Program Files\` | 64-Bit Programme |
| `C:\Program Files (x86)\` | 32-Bit Programme |

---

## Mounten in Linux

```bash
# Gerät mounten
sudo mount /dev/sdc1 /mnt

# Gemountete Geräte anzeigen
sudo mount
df -h
```

> In Windows: Laufwerksbuchstaben (C:, D:) = automatisches Mounten

---

## Verknüpfungen

→ [[03 - Linux Kennenlernen]]
→ [[05 - Dateisystemrechte]]
→ [[Befehle-Cheatsheet]]
