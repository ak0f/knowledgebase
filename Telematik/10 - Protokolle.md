# Protokolle

**Fach:** Telematik
**Tags:** #TCP #UDP #ICMP #Port #Socket #HTTP #DNS #SSH

---

## Lernziele

- [ ] Protokoll, Port und Socket erklären
- [ ] TCP und UDP vergleichen (Vor- und Nachteile, Einsatz)
- [ ] Three-Way-Handshake erklären
- [ ] ICMP erklären (ping, traceroute)
- [ ] Applikationsprotokolle mit Port, Transport und Layer nennen

---

## Grundidee

Ein Protokoll ist ein **Satz Regeln**: gleiche Sprache (gleiche Befehle), gleiche Reihenfolge (erst Verbindung, dann Daten), gleiches Format (wo im Paket steht welche Information).

### Port und Socket
- **IP-Adresse** → führt zum **Gerät** (wie die Strassennummer)
- **Port** → führt zum **Programm** (wie die Wohnungsnummer)
- **Socket** = IP und Port zusammen: `IP:Port`

**Beispiel:** Browser ruft eine Webseite auf
`192.168.1.10:52431` (Client) → `142.250.74.36:443` (HTTPS-Server)

Eine Verbindung besteht immer aus **zwei Sockets**. Der Server hört auf einem festen Port (443), der Client nimmt einen zufälligen freien Port.

---

## Transport (Layer 4)

### UDP – User Datagram Protocol (schnell)
- **Nicht verbindungsorientiert**, sendet sofort ohne Verbindungsaufbau
- Stellt Daten am richtigen Port zu (z. B. Port 53 für DNS)
- Prüfsumme erkennt kaputte Pakete → werden **verworfen**, nicht neu geschickt
- Header nur **8 Byte**: Source Port, Destination Port, Länge, Prüfsumme

| Vorteile | Nachteile |
|----------|-----------|
| schneller als TCP | keine Garantie, dass ein Paket ankommt |
| sehr wenig Overhead | Reihenfolge nicht garantiert |
| spart Netzressourcen bei kleinen Datenmengen | |

**Einsatz:** Geschwindigkeit wichtiger als Vollständigkeit → Video-/Audio-Streaming, Gaming.

### TCP – Transmission Control Protocol (sicher)
- **Verbindungsorientiert**: bleibt offen, bis sie ausdrücklich geschlossen wird
- Aufbau mit **Three-Way-Handshake**
- **Sequenznummern** nummerieren jedes Segment → Empfänger sortiert richtig
- **Acknowledgments** bestätigen jedes Paket; fehlt eine Bestätigung → neu gesendet
- **Fenstergrösse** steuert, wie viel gleichzeitig unterwegs ist
- Header-Felder: Source/Destination Port, Sequence Number, Acknowledgment Number, Flags, Fenstergrösse

| Vorteile | Nachteile |
|----------|-----------|
| Ankunft garantiert | langsamer als UDP |
| Reihenfolge garantiert | viel Overhead (nicht durch Daten nutzbarer Traffic) |
| passt Datenfluss an die Verbindung an | |

**Einsatz:** jedes Byte muss ankommen → Webseiten, E-Mail, Dateiübertragung.

### Three-Way-Handshake
`SYN` → `SYN-ACK` → `ACK` (Client – Server – Client)

---

## ICMP – Internet Control Message Protocol (Layer 3)

- Transportiert **keine Nutzdaten**, sondern Meldungen über das Netz: Ziel nicht erreichbar, Zeitüberschreitung, Echo
- **Kein Port**
- Bekannt von **ping** (ist der andere Rechner erreichbar?) und **traceroute** (welchen Weg nimmt das Paket?)

---

## Applikationsprotokolle

| Protokoll | Port | Transport | Layer | Aufgabe |
|-----------|------|-----------|-------|---------|
| **HTTP** | 80 | tcp | 7 | Webseiten an den Browser |
| **HTTPS** | 443 | tcp | 7 | HTTP über TLS |
| **FTP** | 20 / 21 | tcp | 7 | Dateitransfer (Client-Server) |
| **SSH** | 22 | tcp | 7 | verschlüsselte Konsole auf fernem Gerät |
| **SMTP** | 25 | tcp | 7 | Mail-Versand (Client → Server → Ziel) |
| **IMAP** | 143 | tcp | 7 | Mails auf einem Server verwalten |
| **NTP** | 123 | udp | 7 | Zeitsynchronisation |
| **DNS** | 53 | udp (auch tcp) | 7 | Namen ↔ IP-Adressen |
| **TLS** | – | tcp | 5 | Verschlüsselung (Transport Layer Security) |
| **TCP** | – | – | 4 | sicherer Transport |
| **UDP** | – | – | 4 | schneller Transport |
| **ICMP** | – | – | 3 | Ping, Traceroute |

> **Für dein Poster:** diese Tabelle auswendig können.

---

## Verknüpfungen

→ [[03 - Schichtenmodelle]]
→ [[11 - DNS]]
→ [[17 - Analysetools]]
→ [[00 - MOC]]
