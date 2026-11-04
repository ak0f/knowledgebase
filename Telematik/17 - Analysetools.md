# Analysetools

**Fach:** Telematik
**Tags:** #Troubleshooting #arp #ipconfig #ping #tracert #netstat #nslookup #Wireshark

---

## Lernziele

- [ ] Netzwerkprobleme systematisch von unten nach oben eingrenzen
- [ ] Jedem Layer das passende Tool zuordnen
- [ ] `arp`, `ipconfig`, `ping`, `tracert`, `netstat`, `nslookup` anwenden
- [ ] Wireshark sinnvoll einsetzen (mit Filter)

---

## Hilfe, kein Netz! – Von unten nach oben suchen

1. **Was funktioniert nicht mehr?** Ein Dienst, eine Website, alles? Nur bei einem Gerät oder bei allen?
2. **Schicht für Schicht prüfen**
   - Layer 1 und 2: Kabel und MAC
   - Layer 3: IP
   - Layer 4: Ports
   - Layer 5–7: Dienst und Anwendung
   - Layer 8: **der Mensch**
3. **Nicht raten, messen** – jedes Tool beantwortet genau eine Frage

---

## Werkzeugkasten

| Layer | Tool | Frage |
|-------|------|-------|
| 2 | `arp` | Kenne ich die MAC des Routers? |
| 3 | `ipconfig` | Was hat meine Netzkarte? |
| 3 | `ping` | Ist das Ziel erreichbar? |
| 3 | `tracert` | Welchen Weg nimmt das Paket? |
| 4 | `netstat`, `Test-NetConnection`, `nmap` | Welche Ports/Sockets sind offen? |
| 7 | `nslookup`, `ftp`, `net use`, Testmail | Funktionieren Namen und Dienst? |
| 2–7 | Wireshark | Was läuft wirklich im Netz? |

---

## Layer 2: arp (von der IP zur MAC)

```bash
arp -a    # ARP-Cache anzeigen: ist die MAC des Routers da?
arp -d    # Cache löschen und neu aufbauen lassen
```

---

## Layer 3: ipconfig

```bash
ipconfig            # IP, Maske, Gateway
ipconfig /all       # alle Details: IP, Maske, Gateway, DNS, MAC
ipconfig /release   # DHCP-Adresse zurückgeben
ipconfig /renew     # neue Adresse beim DHCP holen
```

| Beobachtung | Ursache |
|-------------|---------|
| keine IP oder `169.254.x.x` | DHCP antwortet nicht |
| Karte fehlt ganz | Treiber oder NIC deaktiviert |
| falscher Gateway | Weg nach draussen fehlt |

---

## Layer 3: ping (die Reihenfolge macht die Diagnose)

```bash
ping 192.168.1.1      # Befehl, dann Ziel
ping -a 192.168.1.1   # zusätzlich der Hostname
```

Empfohlene Reihenfolge: `127.0.0.1` → eigene IP → Gateway → `8.8.8.8` → Name (z. B. `google.ch`).

> Klappt die IP, aber nicht der Name? Dann ist es **DNS**, nicht das Netz.

---

## Layer 3: tracert

```bash
tracert 8.8.8.8     # statt der IP geht auch ein Name
```

Bleibt die Liste bei einem Hop stehen, liegt das Problem **dort oder dahinter**. `tracert` nutzt wie `ping` das **ICMP**-Protokoll.

---

## Layer 4: Ports und Sockets

```bash
netstat -an                       # offene Netzverbindungen und Ports
Test-NetConnection host -Port 443 # einzelne Sockets testen (PowerShell)
nmap                              # Sockets systematisch scannen (extern nicht erlaubt!)
```

---

## Layer 7: Dienste und Namen

- `nslookup` → welche IP liefert der DNS-Server für einen Namen?
- Dienst direkt ansprechen: `ftp`, `net use` oder eine Testmail senden
- **Zwei Applikationen vergleichen:** geht es in Firefox, aber nicht in Chrome? Dann ist es die App, nicht das Netz

---

## Wireshark – wenn nichts anderes hilft

- Zeigt, was wirklich läuft: Timeouts, falsche Sequenzen, zu viel Verkehr, ICMP-Redirects
- **Ohne Filter keine Übersicht:** `dns`, `http`, `dhcp` oder `ip.addr == deine-Ziel-IP`
- Fremden Verkehr mitschneiden nur im Rahmen des **Datenschutzes**

---

## Verknüpfungen

→ [[03 - Schichtenmodelle]]
→ [[12 - DHCP]]
→ [[11 - DNS]]
→ [[Befehle-Cheatsheet]]
→ [[00 - MOC]]
