# Subnetting

**Fach:** Telematik
**Tags:** #Subnetting #FLSM #CIDR #Netz-ID #Broadcast

---

## Lernziele

- [ ] Erklären wozu man subnettet
- [ ] Netz-ID per Bitwise AND berechnen
- [ ] Broadcast, erste und letzte Host-Adresse bestimmen
- [ ] Ein Netz nach FLSM in gleich grosse Subnetze aufteilen
- [ ] Anzahl Netze und Hosts aus dem Prefix ableiten

---

## Wieso Subnetting?

Ein grosses Netz (z. B. `192.168.1.0/24` mit 254 Hosts) aufteilen, z. B.:

| Subnetz | Zweck |
|---------|-------|
| `192.168.1.0/26` | Büro |
| `192.168.1.64/26` | Gäste |
| `192.168.1.128/26` | Server |

| Vorteil | Erklärung |
|---------|-----------|
| **Sicherheit** | Bereiche voneinander trennen |
| **Ordnung** | jede Abteilung im eigenen Netz |
| **Weniger Last** | Broadcasts bleiben im Subnetz |

---

## Die ganze Idee

**Bits vom Hostteil zum Netzteil verschieben.**

`/24` = 24 Netz-Bits, 8 Host-Bits → `/25` = 25 Netz-Bits, 7 Host-Bits

> Jedes zusätzliche Netz-Bit **verdoppelt** die Anzahl Netze und **halbiert** die Anzahl Hosts pro Netz.

---

## Merktabelle

| CIDR | Maske | Blockgrösse | Nutzbare Hosts | Subnetze aus /24 |
|------|-------|-------------|----------------|------------------|
| /24 | 255.255.255.0 | 256 | 254 | 1 |
| /25 | 255.255.255.128 | 128 | 126 | 2 |
| /26 | 255.255.255.192 | 64 | 62 | 4 |
| /27 | 255.255.255.224 | 32 | 30 | 8 |
| /28 | 255.255.255.240 | 16 | 14 | 16 |

**Nutzbare Hosts = Blockgrösse − 2** (Netzadresse und Broadcast sind belegt) = `2^Host-Bits − 2`

**Anzahl Subnetze** = `2^(Maske neu − Maske original)`

Weiter: /29 → 32 Netze, /30 → 64 Netze, /31 → 128 Netze (aus /24).

---

## Ablauf in 4 Schritten (Beispiel `192.168.1.1/24`)

### 1. IP-Adresse in Binär
```
192      168      1        1
11000000.10101000.00000001.00000001
```

### 2. Subnetzmaske in Binär
```
255      255      255      0
11111111.11111111.11111111.00000000
```

### 3. Bitwise AND → Netz-ID
```
IP    11000000.10101000.00000001.00000001
Maske 11111111.11111111.11111111.00000000
AND   ----------------------------------
Netz  11000000.10101000.00000001.00000000  = 192.168.1.0
```
`1 AND 1 = 1`, alles andere = 0 → alle Host-Bits fallen weg.

### 4. Hostteil alle Bits auf 1 → Broadcast
```
NID  11000000.10101000.00000001.00000000
BC   11000000.10101000.00000001.11111111  = 192.168.1.255
```

### Ergebnis

| Netzadresse | Erste Host-Adresse | Letzte Host-Adresse | Broadcast |
|-------------|--------------------|---------------------|-----------|
| 192.168.1.0 | 192.168.1.1 | 192.168.1.254 | 192.168.1.255 |

`2⁸ − 2 = 254` Hosts (32 Bits total, 24 Netz, 8 Host).

---

## FLSM (Fixed Length Subnet Mask)

Alle Subnetze haben die **gleiche Maske** und sind damit gleich gross.

### Beispiel: `192.168.1.0/24` in 2 Abteilungen

```
Maske alt /24  11111111.11111111.11111111.00000000
Maske neu /25  11111111.11111111.11111111.10000000
```

Das eine zusätzliche Netz-Bit: Netz A = **0**, Netz B = **1**.

| | Netz A | Netz B |
|--|--------|--------|
| Netz | `192.168.1.0/25` | `192.168.1.128/25` |
| Netz-ID | 192.168.1.0 | 192.168.1.128 |
| Hosts | .1 – .126 | .129 – .254 |
| Broadcast | 192.168.1.127 | 192.168.1.255 |
| Nutzbar | 126 | 126 |

Mit `/26` wären es 4 Netze, mit `/27` acht.

---

## Verknüpfungen

→ [[06 - Zahlensysteme]]
→ [[07 - IPv4 und CIDR]]
→ [[09 - Netzplan]]
→ [[00 - MOC]]
