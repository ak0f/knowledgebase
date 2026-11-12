# VLAN Grundlagen

**Fach:** Netzwerktechnik und -Services (03 - VLAN & Trunking & Switching)
**Tags:** #VLAN #Broadcast #AccessPort

---

## Was ist eine Broadcast-Domäne?

Eine Broadcast-Domäne umfasst alle Geräte, die einen Broadcast empfangen.

- Befinden sich alle Geräte im selben Netzwerk, gehören sie auch zur gleichen Broadcast-Domäne.
- Mit VLANs kann ein Netzwerk in mehrere Broadcast-Domänen aufgeteilt werden.
- Dadurch erhalten nur die Geräte innerhalb desselben VLANs die Broadcasts.

**Beispiel:** Ohne VLANs erhalten alle Geräte den Broadcast. Bei 3 VLANs mit je 3 Geräten erreicht ein Broadcast nur noch die 3 Geräte des eigenen VLANs.

![[vlan-broadcast-domaene.png]]

---

## Was ist ein VLAN?

Ein VLAN (**Virtual Local Area Network**) ist eine logische Aufteilung eines Netzwerks in mehrere unabhängige Bereiche.

- Früher wurden Abteilungen durch separate Switches oder eigene Netzwerke getrennt.
- Mit VLANs geht dieselbe Trennung über die Konfiguration der Switches.
- **Ohne VLANs** braucht jede Abteilung ein eigenes physisches Netzwerk.
- **Mit VLANs** laufen verschiedene Benutzergruppen auf derselben Infrastruktur und sind logisch getrennt.

![[vlan-was-ist-ein-vlan.png]]

---

## Access Port

Jeder Anschluss eines Switches kann einem bestimmten VLAN zugewiesen werden. Das nennt man **Access Port**.

- Ein Access Port gehört **immer genau einem VLAN**.
- Ein Computer an diesem Port ist automatisch im zugewiesenen VLAN.
- Der Computer muss nichts über VLANs wissen. Die Zuordnung macht der Switch.

| Switch-Port | VLAN |
|-------------|------|
| Fa0/1 | VLAN 10 (Verwaltung) |
| Fa0/2 | VLAN 20 (Verkauf) |
| Fa0/3 | VLAN 30 (Gäste) |

![[vlan-access-port.png]]

So sieht das im Lab aus:

```
Switch_A(config)# interface range fastethernet 0/4-6
Switch_A(config-if-range)# switchport mode access
Switch_A(config-if-range)# switchport access vlan 10
```

---

## Trunk Port

Die Verbindung zwischen zwei Switches ist ein **Trunk Port**.

- Ein Trunk überträgt **mehrere VLANs gleichzeitig** über ein Kabel.
- Damit der andere Switch weiss, zu welchem VLAN ein Frame gehört, bekommt jeder Frame eine **VLAN-Kennung (Tag)**.
- Das ist der Standard **IEEE 802.1Q**.

![[vlan-trunk-port.webp]]

```
Switch_A(config)# interface fastethernet 0/1
Switch_A(config-if)# switchport mode trunk
```

---

## 802.1Q und VLAN-Tag

Ein normaler Ethernet-Frame hat Quelladresse, Zieladresse und Nutzdaten (Payload). Er hat **keine Info zum VLAN**.

Auf einem Trunk fügt der Switch den **802.1Q-Header (VLAN-Tag)** ein. Darin steht die **VID** (z. B. 10 oder 20).

- Der Empfänger-Switch weiss damit, zu welchem VLAN der Frame gehört.
- Danach entfernt er den Tag wieder, bevor der Frame zum Endgerät geht.
- Das Endgerät sieht nie einen Tag.

![[vlan-ethernet-frame-8021q.webp]]

| Teil im Tag | Bedeutung |
|-------------|-----------|
| TPID = 0x8100 | zeigt: das ist ein 802.1Q-Frame |
| PCP | Priorität |
| DEI | Verwerfen bei Überlast |
| VID | VLAN-ID |

Der Tag ist 4 Byte gross, darum ist der Frame mit Tag etwas länger.

---

## Native VLAN

- Frames des Native VLANs gehen auf dem Trunk **ohne Tag** (auch "untagged VLAN").
- Bei Cisco ist das standardmässig **VLAN 1**.
- VLAN 1 sollte man in produktiven Netzwerken möglichst nicht nutzen.

> **Merksatz:** Die meisten Frames auf einem Trunk haben einen Tag. Frames vom Native VLAN sind die Ausnahme.

Wichtig: Beide Seiten vom Trunk müssen dasselbe Native VLAN haben, sonst gibt es Fehler.

```
Switch_A(config-if)# switchport trunk native vlan 99
```

---

## Access Port vs. Trunk Port

| | Access Port | Trunk Port |
|---|-------------|------------|
| Anschluss für | Endgerät (PC, Server) | anderer Switch |
| VLANs | genau 1 | mehrere |
| Tag | nein | ja (ausser Native VLAN) |
| Befehl | `switchport mode access` | `switchport mode trunk` |

---

## Begriffe (Knowledge Base)

| Begriff | Erklärung |
|---------|-----------|
| **Broadcast** | Nachricht an alle Geräte im Netz (MAC `FF:FF:FF:FF:FF:FF`) |
| **Broadcast-Domäne** | alle Geräte, die denselben Broadcast bekommen. Ein VLAN = eine Broadcast-Domäne |
| **VLAN** | logisch getrenntes Netz auf demselben Switch |
| **VID** | VLAN-ID, die Nummer (1 bis 4094) |
| **Access Port** | Port für Endgeräte, gehört zu genau einem VLAN |
| **Trunk Port** | Port zwischen Switches, überträgt mehrere VLANs |
| **802.1Q** | Standard für das Taggen von VLAN-Frames |
| **VLAN-Tag** | 4 Byte Zusatz im Frame mit der VID |
| **Tagged / Untagged** | mit oder ohne VLAN-Tag |
| **Native VLAN** | VLAN ohne Tag auf dem Trunk (Cisco: VLAN 1) |
| **Frame** | Dateneinheit auf Layer 2 (Ethernet) |
| **Inter-VLAN-Routing** | ein Router (oder Layer-3-Switch) verbindet verschiedene VLANs, denn zwischen VLANs geht es nur über Layer 3 |
| **Management-VLAN** | VLAN, über das man die Switches verwaltet |

**Nützliche Show-Befehle**

| Befehl | Zeigt |
|--------|-------|
| `show vlan brief` | VLANs und ihre Ports |
| `show interfaces trunk` | Trunk-Ports, erlaubte VLANs, Native VLAN |
| `show interfaces <Port> switchport` | Modus des Ports (access/trunk) |

---

## Verknüpfungen

→ [[Aufgabe VLAN & Trunking & Switching]]
