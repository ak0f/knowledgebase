# Netzsicherheit

**Modul:** Netzsicherheit (210)
**Tags:** #Sicherheit #Firewall #Antivirus #Ransomware #WindowsDefender #Updates

---

## Lernziele

- [ ] Wichtigste Windows-Sicherheitseinstellungen kennen und konfigurieren
- [ ] Funktion einer Firewall erklären (was macht sie, was blockiert sie?)
- [ ] **3 Windows Firewall Profile** nennen: Privat, Domäne, Öffentlich
- [ ] Bestehende Firewall-Regeln aktivieren und deaktivieren
- [ ] Neue Firewall-Regeln erstellen
- [ ] Unterschied **Personal Firewall vs. Hardware-Firewall** erklären
- [ ] Antivirus / Windows Defender erklären (Echtzeitscanner, Clouddienst)
- [ ] Ransomware erklären (was ist es, was macht es?)
- [ ] Windows Update im Sicherheitskontext erklären

---

## Windows Sicherheitseinstellungen

Zentrale Suite von Microsoft: **Windows-Sicherheit**

| Bereich | Funktion |
|--------|---------|
| Viren- & Bedrohungsschutz | Antivirus / Defender |
| Firewall & Netzwerkschutz | Windows Firewall |
| App- & Browsersteuerung | Exploit-Schutz, SmartScreen |
| Gerätesicherheit | TPM, Secure Boot |

---

## Antivirus – Windows Defender

- **Microsoft Defender** = integrierter Virenschutz in Windows
- Alternativen: Drittanbieter (Kaspersky, Bitdefender, ESET usw.)

### Funktionen des Virenschutzes:
- **Echtzeitscanner** – überwacht ständig alle Dateizugriffe
- **Onlinescanner** – z.B. https://virustotal.com (Einzeldatei prüfen)
- **Cloudtechnik** – verdächtige Dateien werden in der Cloud analysiert

---

## Ransomware

> **Ransomware = Erpresser-Schadsoftware**

- **Was macht sie:** Verschlüsselt Dokumente/Dateien auf dem PC (und File-Servern)
- **Forderung:** Lösegeld gegen (vermeintliche) Entschlüsselung
- **Schutz:**
  - Aktueller Antivirus
  - Regelmässige Backups (offline!)
  - Keine unbekannten Anhänge öffnen
  - File-Server-Schutz (kontrollierter Ordnerzugriff)

---

## Exploit-Schutz

- Schützt vor Ausnutzung von Software-Schwachstellen
- Konfigurierbar in Windows-Sicherheit → App- & Browsersteuerung

---

## Firewall – Grundlagen

### Was macht eine Firewall?
- **Datenverkehr zulassen oder blockieren**
- Netz / PC gegen Angreifer schützen

### Firewall-Arten

| Art | Beschreibung |
|-----|-------------|
| **Personal / Software Firewall** | Läuft auf dem PC selbst (z.B. Windows Firewall) |
| **Hardware Firewall** | Eigenständiges Gerät im Netzwerk (z.B. Router mit Firewall) |

---

## Windows Firewall – 3 Profile

| Profil | Einsatz | Sicherheit |
|--------|---------|-----------|
| **Privat (Heimnetzwerk)** | Heimnetz – vertrauenswürdig | mittel |
| **Domäne (Arbeitsplatz)** | Firmennetz mit Active Directory | mittel |
| **Öffentliches Netzwerk** | Hotel, Café, Bahnhof WLAN | **hoch** |

> Je nach erkanntem Netzwerk wird automatisch das richtige Profil aktiviert.

---

## Firewall – Regeln verwalten

### Einzelne Apps zulassen / blockieren
- Windows-Sicherheit → Firewall & Netzwerkschutz → App durch Firewall zulassen

### Erweiterte Regeln (Ports, Protokolle)
```
Windows-Sicherheit → Firewall → Erweiterte Einstellungen
  → Eingehende Regeln / Ausgehende Regeln
    → Regel aktivieren / deaktivieren
    → Neue Regel erstellen (Port, Programm, Vordefiniert, Benutzerdefiniert)
```

---

## Windows Update – Sicherheitsaspekt

- **Automatisch aktiviert** (nicht vollständig deaktivierbar)
- Sicherheitsupdates schliessen bekannte Schwachstellen
- Kann verzögert werden, aber **nicht dauerhaft deaktiviert**
- In Unternehmen steuerbar via **GPO / WSUS**

---

## Zusammenfassung – Sicherheits-Dreiklang

```
1. Antivirus (Defender) aktuell halten
2. Firewall aktiviert lassen (richtiges Profil!)
3. Windows Updates installieren
```

---

## Verknüpfungen

→ [[05 - Netzzugang einrichten]]
→ [[04 - Windows Unterhalt und Updates]]
→ [[00 - MOC]]
