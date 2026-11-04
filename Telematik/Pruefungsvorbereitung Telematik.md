# Prüfungsvorbereitung – Telematik

> Hake jedes Lernziel ab wenn du es beherrschst.  
> Bewertung: Minitest (½), SOHO-Projekt (1), Abschlusstest (1)

---

## 01 – Einstieg und Netzarten

- [ ] PAN, LAN, CAN, MAN, WAN mit Beispiel nennen
- [ ] Drahtlos vs. drahtgebunden unterscheiden
- [ ] Simplex, Halb-Duplex, Duplex erklären
- [ ] Unicast, Multicast, Broadcast erklären
- [ ] Vollvermaschung, Stern, Baum mit Vor- und Nachteilen

## 02 – Übertragungsmedien und Stecker

- [ ] Twisted Pair und Cat5e/6/7 erklären
- [ ] Aufbau einer Glasfaser (Kern, Mantel, Coating, Jacket)
- [ ] Kupfer vs. Glas vergleichen (100 m, PoE, Störungen)
- [ ] RJ45, LC, SC zuordnen

## 03 – Schichtenmodelle

- [ ] 7 OSI-Schichten in der richtigen Reihenfolge
- [ ] Aufgaben der OSI-Schichten
- [ ] TCP/IP (4 Schichten) dem OSI zuordnen
- [ ] Encapsulation: Segment, Paket, Frame

## 04 – Netzwerkkomponenten

- [ ] NIC, Switch, Access Point, Router, Firewall mit Layer
- [ ] MAC-Address-Table erklären
- [ ] Broadcast auf Layer 2 (ff:ff:ff:ff:ff:ff) und Layer 3 (255.255.255.255)
- [ ] Default Deny vs. Default Allow
- [ ] Router vs. Gateway, Port vs. NIC

## 05 / 06 – Adressierung und Zahlensysteme

- [ ] MAC (48 Bit), IPv4 (32 Bit), IPv6 (128 Bit) vergleichen
- [ ] Vendor-Code einer MAC erklären
- [ ] Binär ↔ Dezimal umrechnen
- [ ] Hex ↔ Binär umrechnen

## 07 – IPv4 und CIDR

- [ ] Netzteil / Hostteil unterscheiden
- [ ] `/24` ↔ `255.255.255.0`
- [ ] Netzadresse, Broadcast, nutzbare Hosts bestimmen
- [ ] Private Bereiche: 10/8, 172.16/12, 192.168/16
- [ ] APIPA (169.254/16) und Loopback (127/8)

## 08 – Subnetting

- [ ] Netz-ID mit Bitwise AND berechnen
- [ ] Broadcast berechnen
- [ ] Merktabelle /24–/28 (Maske, Blockgrösse, Hosts)
- [ ] FLSM: Netz in 2/4/8 Subnetze teilen
- [ ] Anzahl Subnetze: `2^(neu − alt)`

## 09 – Netzplan

- [ ] Schematisch vs. geographisch
- [ ] Namenskonzept (s1, ge0, sw01, l3sw01)
- [ ] 4 Pflichtangaben auf jedem Plan

## 10 – Protokolle

- [ ] Port und Socket erklären
- [ ] TCP vs. UDP (Vor-/Nachteile, Einsatz)
- [ ] Three-Way-Handshake
- [ ] ICMP: ping, traceroute
- [ ] Ports: HTTP 80, HTTPS 443, FTP 20/21, SSH 22, SMTP 25, IMAP 143, NTP 123, DNS 53

## 11 – DNS

- [ ] FQDN lesen
- [ ] gTLD / sTLD / ccTLD
- [ ] Nameserver, Resolver, Resource Record
- [ ] Rekursiv vs. iterativ

## 12 – DHCP

- [ ] 4 Probleme statischer Adressen
- [ ] DORA
- [ ] Lease und Renew (nach halber Zeit)
- [ ] Broadcast bleibt im Netz, ein Server pro Subnetz, APIPA

## 13 – Routing

- [ ] Routing-Tabelle lesen
- [ ] Next-Hop vs. Exit-Interface
- [ ] Default-Route `0.0.0.0/0`
- [ ] Statisch vs. dynamisch (RIP, OSPF, BGP)
- [ ] Rückroute nicht vergessen

## 14 / 15 – WLAN

- [ ] 2.4 GHz vs. 5 GHz
- [ ] Kanäle 1, 6, 11
- [ ] WiFi 5 / 6 / 7 (802.11ac / ax / be)
- [ ] Ad-Hoc vs. Infrastruktur
- [ ] SSID, WPA2/WPA3, MAC-Filter einordnen
- [ ] Tipps zur Absicherung

## 16 – NAT

- [ ] Warum NAT
- [ ] Source NAT, Destination NAT, Port Forwarding
- [ ] m:1 vs. 1:1
- [ ] Warum kein NAT bei IPv6
- [ ] Switch / Router / Router mit NAT entscheiden

## 17 – Analysetools

- [ ] Fehlersuche von unten nach oben
- [ ] arp, ipconfig, ping, tracert, netstat, nslookup
- [ ] Wireshark-Filter

---

## Verknüpfungen

→ [[00 - MOC]]
→ [[Befehle-Cheatsheet]]
