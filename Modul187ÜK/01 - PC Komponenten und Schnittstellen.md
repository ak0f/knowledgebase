# PC Komponenten und Schnittstellen

**Modul:** PC Komponenten und Schnittstellen (210)
**Tags:** #Hardware #Komponenten #Schnittstellen #CPU #RAM #USB #PCIe

---

## Lernziele

- [ ] Ablauf der Datenverarbeitung erklären: Eingabe → Verarbeitung → Ausgabe
- [ ] Funktion jeder PC-Komponente beschreiben (CPU, Mainboard, RAM, SSD/HDD, NIC, Netzteil)
- [ ] Kriterien für Hardwareanforderungen nennen (Einsatzgebiet: Homeoffice, Business, Gamer)
- [ ] **3 bekannte Peripheriegeräte** nennen
- [ ] Interne Schnittstellen nennen: PCIe, SATA, M.2, SAS
- [ ] Externe Schnittstellen nennen: USB (Versionen + Farben), HDMI, DisplayPort, VGA/DVI, RJ45
- [ ] Unterschied MB/s (intern) vs. Mbit/s (Netzwerk/extern) erklären
- [ ] 32bit vs. 64bit erklären
- [ ] Netzteil-Effizienz 80 PLUS erklären

---

## Datenverarbeitung

```
Eingabe → Verarbeitung → Ausgabe
(Tastatur/Maus)  (CPU/RAM)  (Monitor/Drucker)
```

---

## Komponenten – Überblick

| Komponente | Aufgabe |
|-----------|---------|
| **CPU** | Recheneinheit – verarbeitet Befehle (Herz + Hirn) |
| **Mainboard** | Basis für alle Komponenten, verbindet alles |
| **RAM** | Flüchtiger Arbeitsspeicher – viel schneller als SSD |
| **SSD / HDD** | Dauerhafter Massenspeicher |
| **NIC** | Netzwerkkarte – Kommunikation (LAN/WLAN) |
| **Netzteil** | Stromversorgung aller Komponenten |
| **GPU** | Grafikverarbeitung |

**Baurei­henfolge beim Zusammenbau:**
CPU → Mainboard → RAM → GPU → Netzteil → Gehäuse → SSD/HDD

---

## CPU

- AMD vs Intel – Unterschiede: Cores, GHz, Watt (Energieeffizienz)
- CPU bestimmt den Mainboard-Sockel

### 32bit vs. 64bit

| | 32bit | 64bit |
|--|-------|-------|
| Max. RAM | 4 GB | 512 GB+ |
| Adressraum | ~4 Milliarden | ~18 Exabytes |
| Standard 2026 | veraltet | ✓ Standard |

---

## RAM

- Random Access Memory
- **Flüchtig** – Daten weg bei Stromverlust
- Muss zum Mainboard passen (DDR-Generation)

---

## Massenspeicher

| | HDD | SSD (SATA) | SSD (NVMe M.2) |
|--|-----|-----------|----------------|
| Geschwindigkeit | ~150 MB/s | ~550 MB/s | 3–7 GB/s |
| Kosten | günstig | mittel | höher |
| Robustheit | empfindlich (mechanisch) | robust | robust |
| Anschluss | SATA | SATA | PCIe (M.2) |

---

## Interne Schnittstellen

| Schnittstelle | Einsatz | Geschwindigkeit |
|--------------|---------|----------------|
| **PCIe 4.0** | GPU, NVMe, Erweiterungskarten | ~1.97 GB/s pro Lane |
| **PCIe 5.0** | High-End GPU/SSD | ~3.94 GB/s pro Lane |
| **SATA 3.0** | HDD / günstige SSD | max. ~550 MB/s |
| **M.2** | NVMe SSD, WLAN-Adapter | via PCIe (sehr schnell) |
| **SAS** | Server-Festplatten | bis 24 Gbit/s |

> Interne Einheit: **MB/s oder GB/s** (Bytes)

---

## Externe Schnittstellen – USB

| Version | Farbe | Geschwindigkeit |
|---------|-------|----------------|
| USB 2.0 | Schwarz/Grau | 480 Mbit/s (~60 MB/s) |
| USB 3.2 Gen 1 | Blau | 5 Gbit/s |
| USB 3.2 Gen 2 | Hellblau/Teal | 10 Gbit/s |
| USB 3.2 Gen 2x2 | Rot | 20 Gbit/s |
| USB4 Gen 3x2 | – | 40 Gbit/s |
| USB4 2.0 | – | 80 Gbit/s |

> USB-C: kein oben/unten, bis 240W Laden

---

## Externe Schnittstellen – Video

| Anschluss | Typ | Besonderheit |
|----------|-----|-------------|
| **VGA** | Analog (1987) | veraltet |
| **DVI** | Digital (1999) | erster digital |
| **HDMI 2.1** | Digital | Bild + Ton, bis 8K, 38.4 Gbit/s |
| **DisplayPort 2.1** | Digital | bis 80 Gbit/s, 4K+ |

---

## Externe Schnittstellen – Netzwerk

| Standard | Geschwindigkeit |
|---------|----------------|
| Fast Ethernet | 100 Mbit/s |
| Gigabit Ethernet | 1 Gbit/s |
| 10 Gigabit Ethernet | 10 Gbit/s |

**WLAN:**
| Standard | Max. |
|---------|------|
| Wi-Fi 4 (802.11n) | 600 Mbit/s |
| Wi-Fi 5 (802.11ac) | 6933 Mbit/s |
| Wi-Fi 6 (802.11ax) | 9600 Mbit/s |

**Bluetooth:** ~10m Reichweite (PAN), aktuell BT 6.0 (2024)

---

## Netzteil – Effizienz

> 80 PLUS Zertifizierung = mindestens 80% Effizienz (Bronze / Silver / Gold / Platinum / Titanium)

**Warum effizientes Netzteil?**
- Stromkosten senken
- Leiserer Betrieb (weniger Abwärme → langsamerer Lüfter)
- Längere Lebensdauer der Bauteile

---

## Bit vs. Byte

| | Einheit | Typischer Einsatz |
|--|---------|------------------|
| **Intern** (SSD, RAM, PCIe) | **MB/s, GB/s** | Dateigrösse pro Sekunde |
| **Netzwerk/USB** | **Mbit/s, Gbit/s** | Signalgeschwindigkeit |

> 1 Byte = 8 Bit → 1 GB/s = 8 Gbit/s

---

## Peripheriegeräte (3 Prüfungsbeispiele)

1. Maus / Tastatur (Eingabe)
2. Monitor / Drucker (Ausgabe)
3. Externe Festplatte (Speicher)

---

## Verknüpfungen

→ [[02 - Windows Installation und Lizenzen]]
→ [[00 - MOC]]
