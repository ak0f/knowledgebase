
Zwei fehlerhafte Netze, von Layer 1 bis Layer 3 analysieren. Pro Szenario: Symptom, Hypothese, Diagnose, Korrektur, Funktionsnachweis.

**Vorgehen:**
1. Ausgangszustand mit `show`-Befehlen sichern
2. Zuerst Verkabelung, Portstatus und Interface-Konfiguration prüfen
3. Danach VLAN-, IP- und Gateway-Einstellungen prüfen
4. Nur die tatsächliche Ursache beheben, so wenig wie möglich ändern
5. Tests wiederholen und das Resultat dokumentieren

Dateien: `Troubleshooting Home_Net.pkt` (Aufgabe 1) und `Troubleshooting Ethernet.pkt` (Aufgabe 2)

---

## Aufgabe 1 – Heimnetz mit Internet (Home_Net)

Desktop, Printer und DNS-Server hängen am Wireless_Internet_Router (WRT300N), dahinter der ISP-Router mit Web-Server w1 und w2. Der WRT300N hat keine Konsole, er wird über den Reiter GUI konfiguriert.

### Ausgangszustand

- `ipconfig /all` (FastEthernet0): IP 192.168.10.11, Maske 255.255.255.0, **Gateway 0.0.0.0**, DNS-Server 0.0.0.0
- Bluetooth-Interface: 0.0.0.0, wird nicht benutzt und ist nicht der Fehler
- `ping 192.168.10.1`: 4 von 4 OK (TTL 255), der Router im lokalen Netz ist erreichbar
- ping gateway: OK, ping dns: OK

### Symptom

Noch offen: Browser mit `w1` und `w2` testen und notieren.

### Hypothese

Layer 3: Am Desktop ist kein Default Gateway gesetzt. Dadurch sind Ziele ausserhalb von 192.168.10.0/24 (Internet) nicht erreichbar.

### Diagnose

- Noch zu prüfen: Gateway-IP im Wireless-Router (GUI → Setup → Basic Setup)
- Noch zu prüfen: DNS-Server-Eintrag (Services → DNS, Einträge `w1` und `w2`)
- Noch zu prüfen: ISP-Router mit `show ip interface brief`

### Korrektur

Noch offen.

### Funktionsnachweis

Noch offen: Ping zum Gateway und ISP, Browser `w1` und `w2`.

---

## Aufgabe 2 – Zwei Switches mit DHCP (Ethernet)

PC1 und PC2 hängen an Switch0, PC3, PC4 und der DHCP-Server an Switch1. Die Switches sind über Fa0/3 verbunden. Am Anfang waren alle Links rot.

### Ausgangszustand (Befehle: `show interfaces status`, `show running-config`)

| Gerät | Port | Fund |
|-------|------|------|
| PC1 | Strom | ausgeschaltet («Device must be powered on») |
| Switch0 | Fa0/1 (PC1) | `shutdown`, Status `disabled` |
| Switch0 | Fa0/2 (PC2) | `speed 100` fest gesetzt |
| Switch1 | Fa0/1 (PC3) | `duplex half` fest gesetzt |
| Switch1 | Fa0/24 (DHCP-Server) | Status `disabled` |

Alle anderen Ports standen auf `notconnect`.

### Symptom

Alle Links sind rot. Die PCs erreichen den DHCP-Server und die anderen PCs nicht.

### Hypothese

Layer 1: Ports sind ausgeschaltet oder falsch konfiguriert, PC1 ist ausgeschaltet. Dazu fällt bei den Kabeln auf, dass PC1 ↔ Switch0 gestrichelt (Crossover) ist und Switch0 ↔ Switch1 durchgezogen (Straight-Through). PC an Switch braucht Straight-Through, Switch an Switch braucht Crossover.

### Diagnose

- `show interfaces status` auf beiden Switches
- `show running-config` auf Switch0
- PC1: Config-Reiter → Fehlermeldung «Device must be powered on»

### Korrektur

- PC1: Im Reiter Physical den Power-Knopf eingeschaltet (er wurde grün)
- Switch0: `interface fastEthernet 0/1` → `no shutdown`, `interface fastEthernet 0/2` → `no speed`
- Switch1: `interface fastEthernet 0/24` → `no shutdown`, `interface fastEthernet 0/1` → `duplex auto`

Nach diesen Korrekturen waren alle Ports noch `notconnect`. Es gibt also noch einen weiteren Fehler auf Layer 1.

### Nächste Schritte

- Endgeräte prüfen: Power-Knopf bei PC2, PC3, PC4 und beim DHCP-Server
- Netzwerkkarte prüfen: Config → FastEthernet0, Port Status On, Bandwidth und Duplex auf Auto
- Kabeltypen prüfen und tauschen: PC1 ↔ Switch0 Straight-Through, Switch0 ↔ Switch1 Cross-Over

### Funktionsnachweis

Noch offen: `show interfaces status` mit `connected`, `ipconfig` mit Adresse vom DHCP-Server, Ping zwischen den PCs.

---

## Wichtigste Befehle

| Befehl | Bedeutung |
|--------|-----------|
| `show interfaces status` | Status, VLAN, Duplex und Speed aller Ports |
| `show ip interface brief` | Status und IP aller Interfaces (Router) |
| `show running-config` | aktuelle Konfiguration |
| `no shutdown` | Interface einschalten |
| `speed auto` / `no speed` | Geschwindigkeit wieder automatisch |
| `duplex auto` | Duplex wieder automatisch |
| `ipconfig /all` | IP, Maske, Gateway, DNS und DHCP am PC |
| `ipconfig /renew` | neue Adresse vom DHCP-Server holen |

Status `disabled` = Port mit `shutdown` ausgeschaltet. Status `notconnect` = eingeschaltet, aber kein Gerät erreichbar (Kabel, Gegenstelle aus).
