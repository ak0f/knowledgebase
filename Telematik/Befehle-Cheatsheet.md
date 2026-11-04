# Befehle-Cheatsheet – Telematik

> Netzwerk-Befehle auf einen Blick (Windows)

---

## Layer 2 – arp

| Befehl | Funktion |
|--------|----------|
| `arp -a` | ARP-Cache anzeigen (IP ↔ MAC) |
| `arp -d` | Cache löschen und neu aufbauen lassen |

## Layer 3 – ipconfig

| Befehl | Funktion |
|--------|----------|
| `ipconfig` | IP, Subnetzmaske, Gateway |
| `ipconfig /all` | zusätzlich MAC, DHCP-Server, Lease-Zeiten, DNS |
| `ipconfig /release` | DHCP-Adresse zurückgeben |
| `ipconfig /renew` | neue Adresse beim DHCP holen |

## Layer 3 – ping / tracert

| Befehl | Funktion |
|--------|----------|
| `ping 127.0.0.1` | TCP/IP lokal OK? |
| `ping 192.168.1.1` | Gateway erreichbar? |
| `ping 8.8.8.8` | Internet erreichbar? |
| `ping google.ch` | DNS + Erreichbarkeit |
| `ping -a 172.217.19.3` | Reverse-DNS-Name zur IP |
| `tracert 8.8.8.8` | Weg des Pakets verfolgen (ICMP) |

## Layer 4 – netstat / Test-NetConnection

| Befehl | Funktion |
|--------|----------|
| `netstat -an` | offene Verbindungen und Ports |
| `Test-NetConnection host -Port 443` | einzelnen Socket testen (PowerShell) |
| `nmap` | Sockets scannen (extern nicht erlaubt) |

## Layer 7 – nslookup

| Befehl | Funktion |
|--------|----------|
| `nslookup google.ch` | IP zu einem Namen abfragen |

---

## Wireshark-Filter

`dns` · `http` · `dhcp` · `ip.addr == 192.168.1.1`

---

## Fehlersuche – Reihenfolge

1. `ipconfig` → gültige IP? (nicht `169.254.x.x`)
2. `ping 127.0.0.1` → TCP/IP lokal?
3. `ping [Gateway]` → Router erreichbar?
4. `ping 8.8.8.8` → Internet erreichbar?
5. `ping google.ch` / `nslookup` → DNS OK?
6. `tracert` → wo bricht der Weg ab?

---

## Verknüpfungen

→ [[17 - Analysetools]]
→ [[00 - MOC]]
