# Windows Installation und Lizenzen

**Modul:** Windows Installation und Lizenzen (210)
**Tags:** #Windows #Installation #Lizenz #EULA #OEM #TPM

---

## Lernziele

- [ ] **Windows 11 Mindestanforderungen** nennen (6 Punkte)
- [ ] Windows 11 Versionen nennen und unterscheiden
- [ ] Unterschied OEM-Lizenz vs. normale Lizenz erklären
- [ ] **Lizenzierungsmodelle** kennen: proprietär vs. Open-Source, MAK, KMS
- [ ] EULA erklären – was ist es, was bedeutet Zustimmung?
- [ ] Konsequenzen von Raubkopien nennen
- [ ] Installationsschritte kennen (Sprache, Tastatur, Partition, Datenschutz)
- [ ] Datenschutz bei Windows 11 kennen (Telemetriedaten, Berechtigungen)

---

## Windows 11 – Mindestanforderungen

| Anforderung | Wert |
|------------|------|
| CPU | 1 GHz, min. 2 Kerne, 64-bit |
| RAM | 4 GB |
| Speicher | 64 GB |
| Firmware | **UEFI** mit Secure Boot |
| TPM | **Version 2.0** |
| Grafik | DirectX 12, WDDM 2.0 Treiber |
| Display | min. 720p, >9 Zoll diagonal |

> **Prüfungsfallen:** UEFI + Secure Boot + TPM 2.0 = Pflicht!

---

## Windows 11 – Versionen

| Version | Zielgruppe |
|---------|-----------|
| **Home** | Privatanwender |
| **Pro** | Profis/KMU |
| **Pro for Workstation** | Hochleistungs-Workstations |
| **Enterprise** | Grossunternehmen |
| **Education** | Bildungseinrichtungen |
| **Pro Education** | Schulen |

**Namenszusätze:**
- N = ohne Windows Media Player
- K = ohne Skype (Südkorea)
- E = ohne Internet Explorer
- SL = Single Language
- LTSB = Long Term Service Branch

---

## Lizenzierungsmodelle

### Proprietär (Closed-Source)
- Windows, macOS
- Programmcode nur beim Hersteller
- Oft kostenpflichtig (auch Freeware/Shareware möglich)
- Hersteller bestimmt Nutzungsbedingungen

### Open-Source
- Linux (GPL, BSD, MIT usw.)
- Programmcode frei zugänglich
- Grundsätzlich gratis
- Verdienst durch Support/Spenden

---

## Lizenz-Typen (Aktivierung)

| Typ | Einsatz | Beschreibung |
|-----|---------|-------------|
| **Windows-Schlüssel** | Privat | Einmalig, an Hardware gebunden |
| **Digitale Lizenz** | Privat/OEM | An Hardware (Motherboard) gebunden |
| **OEM-Lizenz** | OEM-Geräte | Günstig, nicht übertragbar |
| **MAK** | Unternehmen | Multiple Activation Keys |
| **KMS** | Unternehmen | Key Management Service (intern) |

### OEM vs. normale Lizenz
| | OEM | Retail |
|--|-----|--------|
| Preis | günstiger | teurer |
| Übertragbarkeit | nicht übertragbar | übertragbar |
| Support | Gerätehersteller | Microsoft |

---

## EULA – End User License Agreement

> EULA = AGB (Allgemeine Geschäftsbedingungen) für Software

- **Bedeutung:** Benutzungsbestimmungen – Regeln zur Verwendung der Software
- Zustimmung = rechtlich bindend
- Beispiel: Updatezwang bei Windows 11
- **Raubkopie:** Nutzung ohne gültige Lizenz → rechtliche Konsequenzen (Urheberrechtsverletzung, Bussen, Klagen)

---

## Installation – Ablauf

1. Sprache und Tastaturlayout wählen
2. Partitionierung festlegen
3. **Wichtig:** Bei Neuinstallation gewünschte Partition formatieren!
4. Datenschutz & Berechtigungen konfigurieren

---

## Datenschutz

| Typ | Beschreibung |
|-----|-------------|
| Windows-Berechtigungen | Systemzugriff (Standort, Kamera, Mikro) |
| App-Berechtigungen | Pro-App Zugriff |
| Telemetriedaten | Microsoft sammelt Diagnosedaten – einschränkbar, aber nicht vollständig abschaltbar (ausser Enterprise/Education) |

---

## Verknüpfungen

→ [[01 - PC Komponenten und Schnittstellen]]
→ [[03 - Windows Konfiguration]]
→ [[00 - MOC]]
