# Einstieg und Netzarten

**Fach:** Telematik
**Tags:** #Netzwerk #Topologie #LAN #WAN #Duplex #Broadcast

---

## Lernziele

- [ ] Erklären was ein Netz / Telematik ist
- [ ] Netze nach Ausdehnung unterscheiden (PAN, LAN, CAN, MAN, WAN)
- [ ] Drahtlos vs. drahtgebunden unterscheiden
- [ ] Simplex, Halb-Duplex, Duplex erklären
- [ ] Unicast, Multicast, Broadcast erklären
- [ ] Topologien mit Vor- und Nachteilen nennen (Vollvermaschung, Stern, Baum)

---

## Was ist ein Netz?

- **Elektronische Kommunikation** zwischen mindestens **zwei Endpunkten**
- Gerät A ↔ ein Medium ↔ Gerät B
- Idee des ersten Netzes (**ARPANET**, Kalter Krieg): Ressourcen teilen, damit ein atomarer Schlag nicht das ganze Militär lahmlegt
- Das Internet wächst exponentiell

---

## Netzarten nach Ausdehnung

| Kürzel | Name | Beispiel |
|--------|------|----------|
| **PAN** | Personal Area Network | Handy und Bluetooth-Headset |
| **LAN** | Local Area Network | das BBC-Office |
| **CAN** | Campus Area Network | Universität Bern |
| **MAN** | Metropolitan Area Network | Stadt Bern |
| **WAN** | Wide Area Network | ein Land, oft Synonym für die Welt |

> Die ganze Welt wäre eigentlich ein **GAN** (Global Area Network).

---

## Nach Verbindungsart

| Drahtlos | Drahtgebunden |
|----------|---------------|
| Mobile Daten (3G, LTE, 5G) | Edunet-Gerät (LAN-Kabel) |
| WLAN zuhause / im Zug | |

---

## Übertragungsrichtung

| Art | Bedeutung |
|-----|-----------|
| **Simplex** | Man hört nur zu (eine Richtung) |
| **Halb-Duplex** | Sprechen und hören, aber **nicht gleichzeitig** |
| **Duplex** (Voll-Duplex) | Sprechen und hören **gleichzeitig** |

---

## Adressierungsart (Cast)

| Art | Bedeutung | Merksatz |
|-----|-----------|----------|
| **Unicast** | ein Empfänger | «Hey du!» |
| **Multicast** | eine Gruppe | «Hey ihr!» |
| **Broadcast** | alle im Netz | «Hey!» |

---

## Topologien

### Vollvermaschung
- **Vorteile:** grosse Bandbreite zu jedem Gerät; Ausfall eines Geräts/einer Verbindung hat keinen Einfluss auf die anderen
- **Nachteil:** viel Hardware und Kabel, sehr teuer

### Sternnetz
- **Vorteile:** Ausfall eines Teilnehmers ohne Folgen; hohe Übertragungsrate mit Switch; einfach erweiterbar; verständlich; leichte Fehlersuche
- **Nachteile:** fällt der Zentralrechner (z. B. Switch) aus, ist das Netz lahmgelegt; zentraler Knoten kann zum Flaschenhals werden

### Baum
- **Vorteile:** einfache Konstruktion (z. B. Gebäudeverkabelung); einfach erweiterbar; übersichtlich; relativ günstig
- **Nachteile:** Ausfall eines Vermittlungsgeräts schneidet den ganzen unteren Zweig ab; Schwachstelle zentraler Knoten (Switch)

---

## Kombinieren

Die Merkmale sind unabhängig. Theoretisch gibt es ein **drahtloses Simplex-Broadcast-CAN-Sternnetz**.

---

## Verknüpfungen

→ [[02 - Uebertragungsmedien und Stecker]]
→ [[00 - MOC]]
