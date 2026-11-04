# IPv4 und CIDR

**Fach:** Telematik
**Tags:** #IPv4 #CIDR #Netzmaske #PrivateIP #APIPA

---

## Lernziele

- [ ] Netzteil und Hostteil unterscheiden
- [ ] CIDR-Schreibweise lesen (`/24`) und in Netzmaske umwandeln
- [ ] Entscheiden ob zwei Adressen im gleichen Netz sind
- [ ] Netzadresse, Broadcast und nutzbare Hosts bestimmen
- [ ] Private Adressbereiche, APIPA und Loopback nennen

---

## Aufbau: Netzteil und Hostteil

- IPv4 = 32 Bits = 4 Oktette zu je 8 Bits
- **Gleicher Netzteil = gleiches logisches Netz**
- **Hostteil** = der Bereich, den wir für die Geräte im Netz vergeben

---

## CIDR

Der Slash sagt, nach wie vielen Bits von links der **Netzteil** endet.

`192.168.1.1/24` → 24 Netz-Bits, 8 Host-Bits

### Gleiches Netz oder nicht? (Beispiel /24)

| Gleiches Netz (direkt) | Anderes Netz (Router nötig) |
|------------------------|------------------------------|
| 192.168.1.1, .10, .123, .254 | 192.168.2.5, 172.16.1.74, 10.0.10.23, 85.10.95.66 |

### Netzmaske: zwei Schreibweisen

`/24` = `255.255.255.0` = `11111111.11111111.11111111.00000000`

Die **1er markieren den Netzteil**, die 0er den Hostteil.

| CIDR | Netz-Bits | Host-Bits |
|------|-----------|-----------|
| /8 | 8 | 24 |
| /16 | 16 | 16 |
| /24 | 24 | 8 |
| /32 | 32 | 0 |

---

## Spezielle Adressen

| Adresse | Host-Bits | Beispiel (192.168.1.0/24) |
|---------|-----------|---------------------------|
| **Netzadresse** | alle **0** | `192.168.1.0` |
| **Broadcast** | alle **1** | `192.168.1.255` |
| nutzbare Hosts | dazwischen | `.1` bis `.254` = **254** |

> Zwei Netze nebeneinander (z. B. 192.168.10.0/24 und 192.168.20.0/24): Geräte im gleichen Netz sprechen direkt, über die Netzgrenze braucht es einen **Router**.

---

## Private Adressen

**Wieso?** IPv4 hat nur rund 4 Mrd. Adressen. Darum darf jedes Netz dieselben privaten Adressen intern nochmals verwenden.

- Nur intern erlaubt, in jedem privaten Netz (auch mehrfach auf der Welt)
- Werden **nicht geroutet**
- Der Router übersetzt sie per **NAT** auf eine öffentliche IP (→ [[16 - NAT]])

| Adressbereich | Maske | CIDR |
|---------------|-------|------|
| `10.0.0.0` – `10.255.255.255` | 255.0.0.0 | `10.0.0.0/8` |
| `172.16.0.0` – `172.31.255.255` | 255.240.0.0 | `172.16.0.0/12` |
| `192.168.0.0` – `192.168.255.255` | 255.255.0.0 | `192.168.0.0/16` |
| `169.254.0.0` – `169.254.255.255` (**APIPA**) | 255.255.0.0 | `169.254.0.0/16` |
| `127.0.0.0` – `127.255.255.255` (**Loopback**) | 255.0.0.0 | `127.0.0.0/8` |

- **APIPA:** Client hat keinen DHCP erreicht und vergibt sich selbst eine Adresse → [[12 - DHCP]]
- **Loopback:** das eigene Gerät (`127.0.0.1`)

---

## Verknüpfungen

→ [[06 - Zahlensysteme]]
→ [[08 - Subnetting]]
→ [[16 - NAT]]
→ [[00 - MOC]]
