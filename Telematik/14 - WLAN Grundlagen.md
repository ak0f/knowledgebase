# WLAN Grundlagen

**Fach:** Telematik
**Tags:** #WLAN #WiFi #802.11 #Frequenz #Kanal

---

## Lernziele

- [ ] WLAN von anderen drahtlosen Technologien abgrenzen
- [ ] 2.4 GHz und 5 GHz vergleichen
- [ ] Die wichtigsten 802.11-Standards nennen
- [ ] Ad-Hoc und Infrastruktur unterscheiden
- [ ] Warum nur Kanal 1, 6, 11 im 2.4-GHz-Band
- [ ] Gründe für langsames WLAN und Gegenmittel nennen

---

## Drahtlose Kommunikation

WLAN ist nur eine von vielen: **Wi-Fi, Bluetooth, RFID/NFC, Mobilfunk 4G/5G, Infrarot, Satellit**. Alle senden über Funkwellen. Unterschied sind Frequenz, Reichweite und Leistung.

**Ausdehnung:** WPAN (Personal), WLAN (Local), WWAN (Wide).

---

## Frequenzbänder

WLAN funkt im **ISM-Band**: ein Frequenzbereich, den alle ohne Bewilligung nutzen dürfen. Genau darum wird es dort auch eng.

| | 2.4 GHz | 5 GHz |
|--|---------|-------|
| Reichweite | reicht weiter, geht durch Wände | kürzer |
| Geschwindigkeit | langsamer, mehr Störungen | schneller, weniger gestört |
| Kanäle | nur **3 ohne Überlappung** | viele freie Kanäle |
| Outdoor | auch outdoor erlaubt | oft nur indoor erlaubt |

---

## 802.11 – die wichtigsten Standards

| Protokoll | Name | Frequenz | Durchsatz brutto |
|-----------|------|----------|------------------|
| 802.11ac | WiFi 5 | 5 GHz | 6 900 Mbit/s |
| 802.11ax | WiFi 6 | 2.4 + 5 GHz | 11 000 Mbit/s |
| 802.11be | WiFi 7 | 2.4 + 5 + 6 GHz | bis 64 000 Mbit/s |

**Brutto** ist der theoretische Wert. **Netto** bleibt in der Praxis etwa **ein Drittel** davon.

---

## Betriebsarten

| Art | Beschreibung |
|-----|--------------|
| **Ad-Hoc** | Geräte verbinden sich direkt untereinander |
| **Infrastruktur** | Geräte verbinden sich über einen **Access Point** |

In der Praxis fast immer **Infrastruktur**. Der Access Point ist dabei eine **Bridge von Funk auf Kabel**.

---

## Performance

### Kanäle im 2.4-GHz-Band
Die Kanäle überlappen sich. Nur **1, 6 und 11** überlappen nicht. Alle anderen Kanäle stören einander.

### Warum wird WLAN langsam?
- Alle Stationen senden im gleichen Frequenzbereich
- **Störquellen:** Nachbar-Netze, Mikrowellen, Bluetooth
- Jede Wand und jeder Meter kostet Leistung

**Gegenmittel:** 5 GHz nutzen, Kanal sinnvoll wählen, Access Points richtig platzieren.

---

## Strahlung – wie gefährlich ist WLAN?

- Hängt ab von Sendeleistung und Distanz zur Antenne
- WLAN-Risiko etwa ein **Tausendstel** des Handyrisikos
- Keine abschliessende gesundheitliche Bewertung möglich
- Handys können bei Herzschrittmachern Störungen verursachen; für 5G sind keine gesundheitlichen Auswirkungen bekannt

---

## Verknüpfungen

→ [[02 - Uebertragungsmedien und Stecker]]
→ [[15 - WLAN Security]]
→ [[00 - MOC]]
