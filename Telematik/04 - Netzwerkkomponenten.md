# Netzwerkkomponenten

**Fach:** Telematik
**Tags:** #NIC #Switch #Router #Firewall #AccessPoint #Gateway

---

## Lernziele

- [ ] Komponenten nennen und ihrer OSI-Schicht zuordnen
- [ ] Switch, Access Point, Router unterscheiden
- [ ] Broadcast auf Layer 2 und Layer 3 erklären
- [ ] Statische vs. dynamische Routen erklären
- [ ] Firewall-Grundregeln (Default Deny / Allow) und Bauformen nennen
- [ ] Router vs. Gateway, Port vs. NIC unterscheiden

---

## Übersicht

| Komponente | Layer | Aufgabe |
|-----------|-------|---------|
| **NIC** | 1–2 | Netzwerkkarte, sendet/empfängt Daten |
| **Switch** | 2 | verbindet Geräte im gleichen IP-Netz (MAC) |
| **Access Point** | 2 | verbindet Funk und Kabel zu einem Netz |
| **Layer-3-Switch** | 2–3 | Switch, der auch routen kann |
| **Router** | 3 | verbindet verschiedene IP-Netze |
| **Firewall** | 3–4 (bis 7) | kontrolliert Datenströme zwischen Netzen |

---

## NIC – Netzwerkkarte

- **Network Interface Card**
- Hat mindestens einen **Port**
- Empfängt und sendet Daten, bereitet sie für höhere Layer auf

---

## Switch (Layer 2)

- Verbindet Geräte im **gleichen IP-Netz**
- Merkt sich, welche **MAC** an welchem Port hängt → **MAC-Address-Table**
- Sendet Daten nur an die richtige MAC-Adresse

### Broadcast
Empfängt ein Switch einen Broadcast, sendet er ihn an **alle Ports im gleichen Netz (VLAN)** weiter.

| Layer 2 – MAC | Layer 3 – IP |
|---------------|--------------|
| `ff:ff:ff:ff:ff:ff` | `255.255.255.255` |
| jedes Gerät kann ihn empfangen (jedes hat eine MAC) | nur Geräte mit gültiger IP-Konfiguration empfangen ihn |

> **VLAN:** getrennte Layer-2-Netze auf einem Switch statt auf separaten Switches.

---

## Access Point (Layer 2)

- Verbindet Funk und Kabel zu **einem** Netz – eine Art **Bridge**
- Arbeitet mit MAC-Adressen, nicht mit IP
- **Ein AP ist kein Router** – er verbindet keine unterschiedlichen IP-Netze

---

## Layer-3-Switch

- Ein Switch, der **routen** kann
- Kann mit Layer-3-Informationen (IP) umgehen
- Muss explizit unterstützt werden

---

## Router (Layer 3)

- Verbindet **verschiedene IP-Netze**, hat darum mindestens **zwei Ports**
- Steht an der äussersten Grenze des Netzes
- Wird oft als **Gateway** der Endgeräte gesetzt
- Führt eine **Routing-Tabelle**: welches Ziel-Netz ist über welchen Nachbarn erreichbar

| Statische Routen | Dynamische Routen |
|------------------|-------------------|
| von Hand eingetragen | Router tauschen Infos über Routing-Protokolle aus (OSPF, RIP, BGP) |
| ändern sich nie von selbst | fällt ein Weg aus, wird umgeleitet |
| gut für kleine, stabile Netze | nötig in grossen Netzen |

→ Details: [[13 - Routing]]

---

## Firewall

- Kontrolliert Datenströme zwischen Netzen
- Filtert nach **IP-Adresse und Port** (Layer 3 + 4); mit Anwendungsfilter bis Layer 7 (z. B. HTTP-Inhalte)

| Grundregel | Bedeutung |
|-----------|-----------|
| **Default Deny** | alles ist zu, erlaubt wird gezielt geöffnet |
| **Default Allow** | alles ist offen, verboten wird gezielt gesperrt |

| Bauform | Beschreibung |
|---------|--------------|
| **Hardware** | eigenes Gerät zwischen zwei Netzen (z. B. LAN und WAN), Konfiguration über Webinterface |
| **Software** | läuft auf einem Host (z. B. Windows Defender Firewall), schützt nur dieses Gerät |

---

## Exkurse

### Router vs. Gateway
- **Router:** immer Layer 3, verbindet IP-Netze
- **Gateway:** kann ein Router sein, muss aber nicht; kann auf höheren Layern arbeiten (z. B. Web-Proxy). Beispiel: die Internet-Box zuhause

### Physischer Port vs. NIC
- Ein physischer Port ist nicht gleich eine NIC
- Die **NIC ist der Chip**, der die Netzwerkfunktion bietet
- Mehrere Ports können sich einen Chip teilen
- Ein Router hat mindestens zwei Ports, aber nicht zwingend zwei Chips

---

## Verknüpfungen

→ [[03 - Schichtenmodelle]]
→ [[09 - Netzplan]]
→ [[13 - Routing]]
→ [[00 - MOC]]
