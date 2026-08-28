# Bootvorgang und BIOS/UEFI

**Modul:** Bootvorgang und BIOS/UEFI (100)
**Tags:** #Boot #BIOS #UEFI #Bootloader #Firmware

---

## Lernziele

- [ ] Den Bootvorgang in seinen Phasen erklären
- [ ] Den Unterschied zwischen BIOS und UEFI beschreiben
- [ ] Erklären, was ein Bootloader macht

---

## Bootvorgang – Die 4 Phasen

```
Strom an → Firmware → POST → Bootloader → Betriebssystem
```

| Phase | Was passiert? | Wo? |
|-------|--------------|-----|
| **Firmware** | Erstes Programm startet | Motherboard |
| **POST** | Hardware wird geprüft | Motherboard |
| **Bootloader** | OS wird gesucht und geladen | Festplatte |
| **OS** | Windows/Linux startet | RAM |

---

## Firmware: BIOS vs. UEFI

> Die Firmware ist ein kleines Programm direkt auf dem Motherboard.

| Merkmal | BIOS (alt) | UEFI (neu) |
|---------|-----------|-----------|
| Alter | seit 1981 | seit ca. 2010 |
| Oberfläche | Nur Text | Grafisch, Maus möglich |
| Festplatten | Max. 2 TB | Über 2 TB |
| Sicherheit | Keine | Secure Boot |

> **Heute haben fast alle PCs UEFI!**

---

## POST (Power-On Self-Test)

Die Firmware prüft beim Start:
- CPU funktionsfähig?
- RAM vorhanden?
- Grafikkarte erkannt?
- Festplatten erkannt?

**Bei Fehlern:** Pieptöne oder Fehlermeldung auf dem Bildschirm

---

## Bootgerät und Bootreihenfolge

Typische Reihenfolge (Firmware sucht in dieser Reihenfolge):
1. USB-Stick
2. Festplatte / SSD
3. Netzwerk

> Darum startet ein USB-Stick vor der Festplatte!

**UEFI aufrufen:**
- Allgemein: `F2`, `F10`, `F12` oder `DEL` beim Start
- EduNet OptiPlex 7040 SFF:
  - `F2` → direkt ins UEFI
  - `F12` → One-Time-Boot (einmalig anderes Gerät auswählen)

---

## Der Bootloader

Kleines Programm auf der **EFI-Partition** der Festplatte.

**Aufgaben:**
1. Betriebssystem finden
2. Betriebssystem in den RAM laden
3. Kontrolle übergeben

| Betriebssystem | Bootloader |
|---------------|-----------|
| Windows | Windows Boot Manager |
| Linux | GRUB |

---

## Secure Boot

- UEFI prüft die **digitale Signatur** des Bootloaders
- Verhindert den Start von **Schadsoftware** vor dem OS
- **Secure Boot deaktivieren = Sicherheitsrisiko!**

**Was bedeutet "signiert"?**
- Hersteller verschlüsselt Bootloader mit geheimem Schlüssel
- UEFI prüft mit öffentlichem Schlüssel: "Ist das wirklich von Microsoft/Ubuntu?"
- Wurde Bootloader verändert (z.B. durch Virus) → Signatur stimmt nicht mehr

---

## Häufige Probleme

| Problem | Ursache | Lösung |
|---------|---------|--------|
| "No bootable device" | Falsche Bootreihenfolge | UEFI: Boot Order prüfen |
| Falsches OS startet | Bootreihenfolge | UEFI: Boot Order ändern |
| Pieptöne beim Start | Hardware-Fehler | RAM/Grafikkarte/CPU prüfen |

---

## Merksatz

> **Strom → Firmware → POST → Bootloader → OS**
> UEFI ist neu, BIOS ist alt. Bootloader liegt auf der Festplatte.

---

## Verknüpfungen

→ [[01 - Software und Hardware]]
→ [[11 - Systemueberwachung und Troubleshooting]]
→ [[09 - Labor EduNet]]
