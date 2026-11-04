# Übertragungsmedien und Stecker

**Fach:** Telematik
**Tags:** #Kupfer #Glasfaser #Ethernet #RJ45 #LWL #WLAN

---

## Lernziele

- [ ] Drahtlose und drahtgebundene Medien nennen
- [ ] Twisted Pair und die Kategorien (Cat5e/6/7) erklären
- [ ] Aufbau einer Glasfaser beschreiben
- [ ] Kupfer und Glas vergleichen
- [ ] Stecker RJ45, LC, SC zuordnen

---

## Übersicht

| Drahtlos | Drahtgebunden |
|----------|---------------|
| Bluetooth, WLAN, NFC | **Kupfer:** Ethernet, Koax (alt!) |
| | **Glas:** LWL (Lichtwellenleiter) |

---

## Drahtlos

### Bluetooth
- Reichweite **40–400 m**
- Meistens für PAN-/LAN-Netzwerke, meist für Sound-Übertragung

### WLAN
- **IEEE 802.11**, diverse Implementationen: 802.11a – 802.11be (**Wi-Fi 7**)
- In Entwicklung: 802.11bn (**Wi-Fi 8**)

---

## Kupfer – Ethernet

- **IEEE 802.3** legt fest, wie Ethernet über Kabel funktioniert
- **Twisted Pair:** vier verdrillte Adernpaare (8 Adern), das Verdrillen schützt vor Störungen
- **Kategorien:** Cat5e, Cat6, Cat7 → höhere Kategorie = höhere Frequenzen (Übertragung) und allenfalls Schirmung (STP/UTP)
- Stecker: **RJ45**

---

## Glasfaser (LWL)

- **Licht statt Strom:** alle anderen Kabel übertragen elektrische Signale, die Glasfaser Lichtimpulse
- Heikel im Umgang: keine engen Biegeradien, nicht quetschen, Glas bricht (Kupfer verbiegt sich nur)

### Aufbau

| # | Teil | Aufgabe |
|---|------|---------|
| 1 | **Kern (Core)** | führt das Licht, nur wenige µm dick |
| 2 | **Optischer Mantel (Cladding)** | kleinere Brechzahl → Totalreflexion |
| 3 | **Schutzbeschichtung (Coating)** | schützt vor Rissen und Feuchtigkeit |
| 4 | **Aussenmantel (Jacket)** | äussere Hülle mit Zugentlastung |

---

## Kupfer oder Glas?

| | Kupfer | Glasfaser |
|--|--------|-----------|
| Signal | elektrische Impulse | Lichtimpulse (im Kern total reflektiert) |
| Länge | max. **100 m** pro Ethernet-Segment | hunderte Meter bis viele km |
| Störungen | störanfällig, darum Schirmung | unempfindlich gegen elektrische Störungen |
| Speisung | Strom über Kabel möglich (**PoE**) | keine Speisung möglich |
| Kosten/Handling | günstig, schnell selbst gesteckt | teurer im Handling |
| Stecker | **RJ45** | **LC**, **SC** |

---

## Stecker

| Stecker | Medium | Merkmale |
|---------|--------|----------|
| **RJ45** | Kupfer | für achtadriges Twisted-Pair-Kabel (8 Adern) |
| **LC** | LWL | klein, meist als Duplex-Paar, heute am verbreitetsten, Switch-zu-Switch mit **SFP-Modulen** |
| **SC** | LWL | grösser, eckig, wird gerade eingesteckt, oft in älteren Verteilern und beim Provider |

---

## Verknüpfungen

→ [[01 - Einstieg und Netzarten]]
→ [[03 - Schichtenmodelle]]
→ [[14 - WLAN Grundlagen]]
→ [[00 - MOC]]
