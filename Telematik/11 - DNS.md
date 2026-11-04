# DNS

**Fach:** Telematik
**Tags:** #DNS #FQDN #TLD #Resolver #nslookup

---

## Lernziele

- [ ] Erklären wozu DNS dient
- [ ] FQDN lesen (von unten nach oben im Namensbaum)
- [ ] TLD-Arten unterscheiden (gTLD, sTLD, ccTLD)
- [ ] Nameserver, Resolver, Resource Record erklären
- [ ] Rekursive vs. iterative Anfrage unterscheiden
- [ ] DNS auf Router/LAN konfigurieren, `ping`, `nslookup` anwenden

---

## Grundidee

**Namen statt Zahlen:** `www.google.ch` ↔ `172.217.19.3`

- Menschen merken sich Namen besser als Zahlen
- **Auflösen:** Name → IP-Adresse und umgekehrt (**Reverse**)
- Port **53**, Kommunikation über TCP und UDP

---

## Hierarchie

Der Namensraum ist ein **Baum**. Der **FQDN** (Fully Qualified Domain Name) ist der komplette Name und wird im Baum von unten nach oben gelesen: `www.de.wikipedia.org.`

### Top Level Domains

| Art | Kürzel | Bedeutung | Beispiele |
|-----|--------|-----------|-----------|
| Generic | **gTLD** | allgemein: kommerziell, gemeinnützig, Provider, Regierung | `.com` `.org` `.net` `.gov` |
| Sponsored | **sTLD** | reserviert für eine bestimmte Branche | `.travel` `.post` |
| Country Code | **ccTLD** | Länderdomains | `.ch` `.de` `.fr` |

Jede TLD wird zentral verwaltet: weltweit die **ICANN**, für die Schweiz **Switch** (nic.ch), für Deutschland **DE-NIC**.

---

## Aufbau: eine verteilte Datenbank

| Begriff | Bedeutung |
|---------|-----------|
| **Nameserver** | verwaltet nur einen kleinen Teil des Namensraums |
| **Resolver** | sitzt auf dem Client und stellt die Anfragen |
| **Resource Record** | ein Eintrag in der Datenbank, z. B. Name → IP |

Kein Server kennt alles. Zusammen bilden sie eine **hierarchische, verteilte Datenbank** nach dem Client-Server-Prinzip.

### Auflösen von `www.google.ch`
- **Rekursiv:** «ich frage weiter, bis ich die Antwort habe»
- **Iterativ:** «ich sage dir nur, wen du als Nächsten fragen musst»

---

## DNS im Netzwerk

- **Router (WAN):** DNS-Server des Providers (ISP) eintragen
- **LAN:** falls vorhanden, interner DNS-Server – kennt die eigenen Geräte und Ressourcen

---

## Selbst prüfen

```bash
ping google.ch          # gibt die IP zum Host zurück und pingt das Ziel (ICMP)
ping -a 172.217.19.3    # gibt den Reverse-DNS-Namen zur IP zurück
nslookup google.ch      # fragt beliebige DNS-Record-Typen ab
```

> Klappt die IP, aber nicht der Name? Dann ist es **DNS**, nicht das Netz.

---

## Verknüpfungen

→ [[10 - Protokolle]]
→ [[12 - DHCP]]
→ [[17 - Analysetools]]
→ [[00 - MOC]]
