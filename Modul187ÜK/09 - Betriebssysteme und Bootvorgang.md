# 08 – Betriebssysteme und Bootvorgang

> **Handlungsziel 6:** Vor der Installation des Betriebssystems die Hardwareanforderungen sowie die Hardwarekompatibilität abklären und die notwendigen Treiber beschaffen.

---

## Lernziele

- [ ] 6.1 Aufgaben, Aufbau und Komponenten eines Betriebssystems kennen und erläutern können
- [ ] 6.2 Vorbereitungsschritte vor der OS-Installation kennen (inkl. UEFI)
- [ ] BIOS vs. UEFI unterscheiden und Vor-/Nachteile erklären
- [ ] Bootvorgang (BIOS und UEFI) erklären
- [ ] Unterschied Bootloader vs. Bootmanager erklären
- [ ] MBR-Struktur kennen

---

## Aufgaben des Betriebssystems

- Schnittstelle zwischen **Benutzer und Hardware**
- Benutzerkommunikation (Input/Output)
- Ausführen von Programmen
- **Verwaltung der Prozessorzeit**
- **Verwaltung des Arbeitsspeichers**
- Verwaltung und Betrieb angeschlossener Geräte
- Schutzfunktionen (z.B. Zugriffsbeschränkungen)

---

## Grundkonzepte

### System Call
- Aufruf einer Anwendung an das Betriebssystem
- Beispiele: Datei öffnen, lesen/schreiben, Befehl ausführen
- Anwendung läuft im **User Mode**, Betriebssystem im **Kernel Mode**

### Multitasking
- Gleichzeitiges Ausführen verschiedener Programme/Prozesse
- CPU verwaltet die Zeitscheiben
- Verschiedene geschützte Speicherbereiche

### Multiuser
- Mehrere Benutzer teilen sich ein System
- Gleichzeitige Nutzung von Ressourcen (RAM, CPU, HDD)
- Schutz der Daten (Dateien, RAM, Cache, Passwörter)

---

## BIOS vs. UEFI

| Merkmal | BIOS | UEFI |
|---------|------|------|
| Partitionstabelle | MBR | GPT |
| Secure Boot | Nein | Ja |
| Max. Disk-Grösse | 2 TB | >2 TB |
| Hardware-Support | Eingeschränkt | Modern |
| Boot-Zeiten | Langsamer | Schneller |
| Updates | ROM-Flashing | Software-Update |
| Kompatibilität | Breite OS-Kompatibilität | Rückwärtskompatibel mit MBR |

**BIOS:** Basic Input Output System
- CMOS-RAM-Chip speichert Einstellungen (braucht Batterie!)
- POST = Power on Self Test (CPU → CMOS → RAM → Grafik → Tastatur/Peripherie)
- Zugang: ESC, Del, F2, F10 oder F12

**UEFI:** Unified Extensible Firmware Interface
- Nachfolger von EFI (Extensible Firmware Interface)
- 64-Bit-Systeme, Secure Boot, PXE, Gerätetreiber
- **Vorteil:** Secure Boot, schnellerer Start, grosse Disks
- **Nachteil:** Internetverbindung vor OS-Boot möglich → Malware-Risiko

---

## MBR-Struktur (512 Byte)

| Inhalt | Grösse |
|--------|--------|
| Boot-Loader | max. 440 Byte |
| Disk-Signatur | 4 Byte |
| Null | 2 Byte |
| Partitionstabelle (max. 4 Einträge) | 64 Byte |
| MBR-Signatur | 2 Byte |
| **Total** | **512 Byte** |

---

## Bootloader vs. Bootmanager

| | Bootloader | Bootmanager |
|---|---|---|
| **Funktion** | Nutzt BIOS/UEFI, startet OS | Bietet OS-Auswahl (Dual-Boot) |
| **Lage** | Im MBR (max. 440 Byte) | Eigene Partition |
| **Beispiel** | GRUB Stage 1 | GRUB, Windows Boot Manager |

---

## Bootvorgang

### Mit BIOS:
```
POST → BIOS (Bootreihenfolge) → MBR → Bootloader Stage 1 → Bootloader Stage 2 → Kernel
```

### Mit UEFI:
```
POST → UEFI → Bootloader (UEFI-Partition) → Kernel
```

---

## Verknüpfungen

→ [[00 - MOC]]
→ [[09 - Datenträger Partitionen und Dateisysteme]]
→ [[Pruefungsvorbereitung UEK]]
