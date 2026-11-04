# 09 – Datenträger, Partitionen und Dateisysteme

> **Handlungsziele 7+8:** Datenträger-Partitionen und Dateisysteme einrichten, Bootmanager und Bootoptionen konfigurieren. Datei- und Verzeichnisstrukturen aufbauen und verwalten.

---

## Lernziele

- [ ] 7.1 Technische Rahmenbedingungen einer Partitionierung kennen
- [ ] 7.2 Datenträger-Verwaltungsstrukturen kennen (MBR/GPT, Partitionstabelle, Bootrecord, Bootloader)
- [ ] 8.1 Eigenschaften und Kompatibilität gängiger Dateisysteme kennen (FAT32, NTFS, exFAT, ext4, APFS, ReFS)
- [ ] 8.3 Konzepte für den Zugriff auf Datenträger kennen (Mount-Befehl, Devicedateien, Treiber)

---

## Speicherarten (langsam → schnell, weit → nah zur CPU)

```
USB/Netzwerk/HDD → SSD → RAM → Cache (L1/L2/L3) → CPU-Register
```

| Typ | Beispiel | Merkmal |
|-----|---------|---------|
| Massenspeicher | HDD, SSD, USB, NAS | Dauerhaft, langsamer |
| Arbeitsspeicher | RAM | Flüchtig, schnell |
| SWAP/Pagefile | Auslagerungsdatei | RAM-Erweiterung auf Disk |
| Cache | L1/L2/L3 | Sehr schnell, nah an CPU |

---

## Partitionen

**Definition:** Unabhängige Speicherabschnitte auf einem Datenträger (SSD, HDD, USB, SD-Karte)

**Verwendungszweck:**
- System-Partition (OS)
- Daten-Partition
- Swap-Partition (Linux)

**Fragmentierung:** Dateien verteilt über nicht zusammenhängende Blöcke
→ Bei SSDs kein Problem/Nachteil mehr!

---

## MBR vs. GPT (Partitionstabellen)

| Merkmal | MBR | GPT |
|---------|-----|-----|
| Alter | Älter, "Legacy" | Nachfolger von MBR |
| OS-Kompatibilität | Breite Kompatibilität | Seit Windows XP 64-Bit |
| Max. Partitionen | 4 primäre | 128 (Windows) / unbegrenzt |
| Max. Partitionsgrösse | 2 TByte | 18 ExaByte |
| Secure Boot | Nein | Ja (mit UEFI) |

---

## Dateisysteme im Vergleich

| Dateisystem | Typ | Max. Partition | Max. Datei | Besonderheit |
|------------|-----|--------------|-----------|-------------|
| **FAT32** | Universal | 8 TiB | 4 GB | Kompatibel mit allen OS; USB-Standard |
| **NTFS** | Windows | 256 TiB | 16 TiB | Standard Windows; Rechteverwaltung; kaum Linux |
| **exFAT** | Universal | 128 PiB | 128 PiB | FAT32-Nachfolger; kein Rechteverwaltung; Kameras |
| **ext4** | Linux | 1 EiB | 16 TiB | Standard Linux |
| **APFS** | macOS | 8 EiB | 8 EiB | Apple-Standard seit 2017; für SSDs optimiert |
| **ReFS** | Windows Server | 35 PB | 35 PB | NTFS-Nachfolger für Server; Schadenserkennung |
| **swap** | Linux | – | – | Auslagerungsspeicher; `mkswap` + `swapon` |
| **SMB 3.x** | Netzwerk | – | – | Windows-Netzwerkfreigaben, Cross-Plattform |
| **NFS** | Netzwerk | – | – | Unix/Linux-Netzwerk-FS; offener Standard |

---

## Partitionierung unter Windows vs. Linux

### Windows
- Laufwerksbuchstaben: C:, D:, E: ...
- Datenträgerverwaltung → formatieren, Laufwerkbuchstaben zuweisen
- Tools: `diskmgmt.msc`

### Linux
- Mountpoints (statt Buchstaben): `/boot`, `/mnt`, `/media/cdrom`
- Partitionen erstellen: `fdisk` oder `cfdisk`
- Dateisystem anlegen: `mkfs` (z.B. `mkfs.ext4`)
- Anzeigen: `df -h` (Belegung), `lsblk` (Struktur)
- Devicedateien: `/dev/sda` (Disk), `/dev/sda1` (Partition 1)

---

## Verknüpfungen

→ [[08 - Betriebssysteme und Bootvorgang]]
→ [[10 - Datei- und Verzeichnisstruktur]]
→ [[00 - MOC]]
