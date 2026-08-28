# Windows Unterhalt und Updates

**Modul:** Unterhalt und Updates (210)
**Tags:** #Windows #Updates #Patchmanagement #Energie #Treiber

---

## Lernziele

- [ ] **3 Möglichkeiten** zum Energiesparen nennen
- [ ] **3 Gründe** nennen, warum Software aktualisiert werden soll
- [ ] **4 Schritte** des Patch-Management-Kreislaufs nennen: Assess → Identify → Evaluate & Plan → Deploy
- [ ] Unterschied OS-Update / Softwareupdate / Treiberupdate / Firmwareupdate erklären
- [ ] Windows Update-Einstellungen kennen (Nutzungszeit, verzögern)
- [ ] **4 Best Practices** Wartung und Energie nennen

---

## Energieverbrauch – Warum wichtig?

- Jedes Gerät **muss produziert** werden → Ressourcenverbrauch
- Jedes Gerät **braucht Strom** → laufende Kosten
- Jedes Gerät **muss entsorgt** werden → Umweltbelastung

---

## Energiespar-Massnahmen (3 nennen!)

1. **Windows Energieplan** wählen oder eigenen erstellen
   - Ausbalanciert / Energiesparmodus / Höchstleistung
2. **Gerät nach Gebrauch ausschalten** – kein Stand-by vergessen
3. **BIOS-Einstellungen** für Energiesparen:
   - Prozessor C-States (C3 oder höher)
   - SATA Link Power Management (LPM) aktivieren
   - PCIe Active State Power Management aktivieren

---

## Energiepläne in Windows

- Vorgefertigte Pläne: Energiesparmodus, Ausbalanciert, Höchstleistung
- Eigene Pläne erstellen: Systemsteuerung → Energieoptionen
- Erweiterte Einstellungen: detaillierte Einstellungen pro Hardware

---

## Warum Software aktualisieren? (3 Gründe)

1. **Sicherheit** – Sicherheitslücken (Bugs) schliessen
2. **Neue Funktionen** – Kompatibilität und Erweiterbarkeit
3. **Stabilität** – Bugfixes, bessere Performance

---

## Update-Typen

| Typ | Beschreibung |
|-----|-------------|
| **OS-Update** | Windows-Aktualisierung (Sicherheit, Funktion) |
| **Softwareupdate** | Anwendungen aktuell halten |
| **Treiberupdate** | Hardware optimal ansprechen |
| **Firmwareupdate** | Firmware von Geräten (UEFI, SSD-Firmware usw.) |

---

## Windows Update

- **Automatisch aktiviert** (kann nicht vollständig deaktiviert werden)
- Kann verzögert werden (Sicherheitsupdates: 0–30 Tage, Funktionsupdates länger)
- In Firmennetzen zentral steuerbar via **GPO / WSUS**
- **Nutzungszeit** festlegen → verhindert ungewolltes Herunterfahren

---

## Patch-Management-Kreislauf (4 Schritte)

```
    Assess
   ↗      ↘
Deploy    Identify
   ↖      ↙
  Evaluate & Plan
```

| Schritt | Bedeutung |
|--------|----------|
| **Assess** | Aktuellen Zustand prüfen – was ist installiert? |
| **Identify** | Verfügbare Updates/Patches identifizieren |
| **Evaluate & Plan** | Patches bewerten, Risiken abwägen, planen |
| **Deploy** | Updates ausrollen und installieren |

> Gut beobachten: https://www.heise.de/security

---

## Best Practices Wartung und Energie (4 Punkte)

1. **OS aktuell halten**
2. **Software aktuell halten**
3. **Treiber aktuell halten**
4. **Geräte nach Gebrauch ausschalten**

---

## Verknüpfungen

→ [[03 - Windows Konfiguration]]
→ [[05 - Netzzugang einrichten]]
→ [[00 - MOC]]
