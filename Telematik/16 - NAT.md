# NAT

**Fach:** Telematik
**Tags:** #NAT #PortForwarding #SourceNAT #DestinationNAT #DMZ

---

## Lernziele

- [ ] Problemstellung hinter NAT erklären
- [ ] Erklären wie NAT mit Ports den Rückweg findet
- [ ] Source NAT, Destination NAT, Port Forwarding unterscheiden
- [ ] m:1 und 1:1 NAT unterscheiden
- [ ] Warum es NAT bei IPv6 nicht gibt
- [ ] Entscheiden: Switch, Router ohne NAT oder Router mit NAT

---

## Problemstellung

- Im Internet braucht es eine **öffentliche IP**
- Private Adressen (`192.168.x.x`) werden **nicht geroutet**
- Eine öffentliche IP pro PC geht nicht auf – IPv4 wäre längst aufgebraucht

**NAT = Network Address Translation:** viele private Adressen teilen sich eine öffentliche.

---

## Was macht NAT?

Der Router **tauscht die Adresse aus**.

### Und der Rückweg? Der Port macht den Unterschied
Der Router führt eine Tabelle: welcher Port gehört zu welchem PC.

| Im LAN (privat) | Im WAN (öffentlich) |
|-----------------|---------------------|
| `192.168.1.2:3618` | `212.103.72.148:3719` |
| `192.168.1.3:3858` | `212.103.72.148:3972` |

Für den PC ist das unsichtbar: er sieht nur seine eigene Adresse und bekommt die richtige Antwort.

---

## Drei Fälle (Richtungen)

| Art | Richtung |
|-----|----------|
| **Source NAT** | vom LAN ins WAN |
| **Destination NAT** | die Antwort findet zurück |
| **Port Forwarding** | Zugriff aus dem WAN ins LAN |

**Beispiel Port Forwarding:** alles auf Port 80 der öffentlichen IP geht an `192.168.1.3:8080`.

---

## Varianten

| Variante | Beschreibung |
|----------|--------------|
| **m : 1** | mehrere Geräte teilen sich eine öffentliche Adresse – der Normalfall im Firmen- und Heimnetz |
| **1 : 1** | eine private Adresse wird immer gegen die gleiche öffentliche getauscht – typisch für Server in einer **DMZ** |

---

## Und bei IPv6?

**NAT gibt es für IPv6 nicht.**

- Genug Adressen für alles (2¹²⁸) – kein Teilen mehr nötig
- Jeder PC ist öffentlich, korrekt konfiguriert ist jedes Gerät direkt erreichbar
- Die **Firewall wird wichtiger**: NAT war nie ein Schutz, aber es hat versteckt

---

## Repetition: Switch oder Router?

| Verbindung | Gerät |
|------------|-------|
| `192.168.1.7/24` ↔ `192.168.1.177/24` | **Switch** (gleiches Netz) |
| `8.8.8.8/8` ↔ `212.103.69.187/29` | **Router ohne NAT** (beide öffentlich) |
| `192.168.3.33/16` ↔ `212.103.69.187/16` | **Router mit NAT** (privat → öffentlich) |

> Gleiches Netz → Switch. Verschiedene Netze → Router. Wechselt privat auf öffentlich → NAT.

---

## Verknüpfungen

→ [[07 - IPv4 und CIDR]]
→ [[13 - Routing]]
→ [[04 - Netzwerkkomponenten]]
→ [[00 - MOC]]
