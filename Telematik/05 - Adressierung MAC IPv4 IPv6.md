# Adressierung: MAC, IPv4, IPv6

**Fach:** Telematik
**Tags:** #MAC #IPv4 #IPv6 #Adressierung

---

## Lernziele

- [ ] Selbständig und auswendig **zwei Arten der Adressierung** benennen (MAC und IP)
- [ ] Aufbau der MAC-Adresse erklären
- [ ] Aufbau von IPv4 und IPv6 erklären
- [ ] Warum es IPv6 gibt

---

## MAC-Adresse

- Jeder **netzwerkfähige Adapter** hat eine eigene MAC – nicht das Gerät als Ganzes
- Ein Notebook mit LAN und WLAN hat darum **zwei MAC-Adressen**
- Fest im Adapter gebrannt, vom Hersteller vergeben, nicht im Netz verteilt

| Gerät | Adapter mit MAC |
|-------|-----------------|
| Kopfhörer | Bluetooth |
| Handy | WLAN, 5G |
| Notebook | LAN, WLAN |

### Aufbau: 48 Bits

```
5C-F9-DD - 88-05-46
 Vendor     Gerät
 (Hersteller) selbst
```

- Hexadezimal (0–9, A–F), in **Zweierblöcken**
- Trenner variieren: `-` `:` `.` oder gar keiner

---

## IPv4

- **32 Bits**, 4 Blöcke zu je 8 Bits (ein Block = **Oktett**)
- Werte pro Oktett: **0–255**, dezimal, mit Punkten getrennt: `192.168.1.1`
- Es gibt rund **4 Mrd.** Adressen (2³²), aber ca. 75 Mrd. Geräte im Internet (IoT) → die Adressen sind ausgegangen

---

## IPv6

- **128 Bits**, 8 Blöcke (**Hextets**), hexadezimal, mit Doppelpunkten getrennt
- Beispiel: `2a00:1450:400a:0802:0000:0000:0000:200e`
- Werte pro Hextet: `0000`–`FFFF`
- **3,4 Sextillionen** Adressen (2¹²⁸)

---

## Vergleich

| | MAC | IPv4 | IPv6 |
|--|-----|------|------|
| Länge | 48 Bits | 32 Bits | 128 Bits |
| Schreibweise | hexadezimal, Zweierblöcke | dezimal, 4 Oktette, Punkte | hexadezimal, 8 Hextets, Doppelpunkte |
| Vergabe | fest im Adapter | wird verteilt | wird verteilt |

---

## Verknüpfungen

→ [[06 - Zahlensysteme]]
→ [[07 - IPv4 und CIDR]]
→ [[04 - Netzwerkkomponenten]]
→ [[00 - MOC]]
