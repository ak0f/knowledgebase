# Netzzugang einrichten

**Modul:** Netzzugang einrichten (210)
**Tags:** #Netzwerk #IP #DHCP #DNS #ipconfig #ping

---

## Lernziele

- [ ] Erkennen ob ein Netzwerkadapter verbunden ist
- [ ] Adaptereinstellungen in Windows finden (Netzwerk und Freigabecenter)
- [ ] **4 wichtige Adressierungsparameter** nennen und erklären: IP, Subnetzmaske, Gateway, DNS
- [ ] Unterschied **statische vs. dynamische IP** (DHCP) erklären
- [ ] Gültige IPv4-Adresse erklären (32-bit, 0–255, .0 und .255 reserviert)
- [ ] Private IPv4-Adressbereiche nennen (3 Bereiche + APIPA)
- [ ] Befehle `ipconfig`, `ping`, `nslookup` anwenden
- [ ] APIPA erklären (169.254.x.x – kein DHCP erreichbar)

---

## Netzwerkadapter

- Typen: **RJ45** (LAN), **WLAN**, **Bluetooth**
- Jede Schnittstelle = ein Adapter in Windows
- Adapter können aktiviert / deaktiviert sein

### Wo finden in Windows?
```
Einstellungen → Netzwerk und Internet → Adapteroptionen
– oder –
Systemsteuerung → Netzwerk und Freigabecenter → Adaptereinstellungen
```

---

## IP-Adressierung – Die 4 wichtigen Parameter

| Parameter | Bedeutung |
|----------|----------|
| **IP-Adresse** | Eindeutige Adresse des Geräts im Netz |
| **Subnetzmaske** | Gibt die Grösse des eigenen Netzes an |
| **Gateway** | Nächste Station, um das Netz zu verlassen (z.B. Router → Internet) |
| **DNS** | Löst Namen in IP-Adressen auf (www.google.com → 157.161.155.144) |

---

## Gültige IPv4-Adresse

- 4 Zahlen zwischen **0 und 255**, getrennt durch Punkte
- Beispiel: `192.168.1.100`
- Technisch: 32-stellige Binärzahl
- **Reserviert:** `.0` (Netzadresse) und `.255` (Broadcast)
- Muss im lokalen Netz **eindeutig** sein!

---

## Statisch vs. Dynamisch (DHCP)

| | Statisch | Dynamisch (DHCP) |
|--|---------|-----------------|
| IP-Vergabe | Manuell konfiguriert | Automatisch vom DHCP-Server |
| Einsatz | Server, Drucker, Router | Normale Clients |
| Vorteil | Immer gleiche IP | Kein manueller Aufwand |

---

## Private IPv4-Adressbereiche (3 kennen!)

| Bereich | Beispiel | Subnetzmaske |
|--------|---------|-------------|
| `192.168.0.0 – 192.168.255.255` | `192.168.1.0/24` | 255.255.255.0 |
| `172.16.0.0 – 172.31.255.255` | `172.16.0.0` | 255.255.0.0 |
| `10.0.0.0 – 10.255.255.255` | `10.0.1.0` | 255.0.0.0 |

### APIPA (Automatic Private IP Addressing)
- **Bereich:** `169.254.0.0 – 169.254.255.255`
- Windows vergibt diese IP **automatisch**, wenn kein DHCP-Server erreichbar
- Bedeutet: **Kein Netzwerk / kein Internet!**

---

## Wichtige Netzwerk-Befehle

```bash
ipconfig           # Zeigt IP, Subnetzmaske, Gateway aller Adapter
ipconfig /all      # Zeigt auch MAC-Adresse, DHCP-Server, DNS
ping 8.8.8.8       # Prüft Erreichbarkeit (Google DNS)
ping google.com    # Prüft DNS-Auflösung + Erreichbarkeit
nslookup google.com  # Löst Domainnamen in IP auf
```

| Befehl | Funktion |
|-------|---------|
| `ipconfig` | Aktuellen Status der Netzwerkadapter anzeigen |
| `ping` | Erreichbarkeit einer Adresse im Netz prüfen |
| `nslookup` | Namen in IP auflösen |

---

## Netzwerkprobleme lösen – Vorgehen

1. `ipconfig` → Habe ich eine gültige IP? (nicht 169.254.x.x)
2. `ping 127.0.0.1` → Funktioniert TCP/IP lokal?
3. `ping [Gateway]` → Ist der Router erreichbar?
4. `ping 8.8.8.8` → Ist das Internet erreichbar?
5. `nslookup google.com` → Funktioniert DNS?

---

## Verknüpfungen

→ [[04 - Windows Unterhalt und Updates]]
→ [[06 - Netzsicherheit]]
→ [[00 - MOC]]
