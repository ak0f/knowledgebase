# Routing

**Fach:** Telematik
**Tags:** #Routing #Router #Routingtabelle #NextHop #DefaultRoute

---

## Lernziele

- [ ] Erklären was ein Router macht (Layer 3)
- [ ] Routing-Tabelle lesen (Ziel-Netz, Next-Hop, Interface)
- [ ] Next-Hop und Exit-Interface unterscheiden
- [ ] Direkt verbundene und statische Routen unterscheiden
- [ ] Default-Route `0.0.0.0/0` erklären
- [ ] Statisches vs. dynamisches Routing vergleichen

---

## Was macht ein Router?

- Vermittelt zwischen Netzen und entscheidet **pro Paket**, wohin es als Nächstes geht
- **Layer 3** – arbeitet mit IP-Adressen
- **Passt kein Eintrag → das Paket wird verworfen**

---

## Die Routing-Tabelle

| Spalte | Frage | Beispiel |
|--------|-------|----------|
| **Ziel-Netz** | Wohin? | `192.168.2.0/24` |
| **Next-Hop** | An wen? (IP des Nachbar-Routers) | `10.0.0.2` |
| **Interface** | Wo raus? (eigener Port) | `G0/1` |

### Nicht verwechseln
- **Next-Hop** = die IP des **Nachbarn** (fremde Adresse im gemeinsamen Netz)
- **Exit-Interface** = der **eigene Port**, durch den das Paket hinausgeht
- Beides muss zusammenpassen: der Next-Hop liegt im Netz des gewählten Interfaces

> **Next-Hop = der Nachbar. Interface = meine Tür.**

---

## Zwei Arten von Einträgen

| Art | Beschreibung |
|-----|--------------|
| **Direkt verbunden** | steht automatisch in der Tabelle; kein Next-Hop nötig, der Router stellt selbst zu |
| **Statische Route** | für ferne Netze; Ziel-Netz, Next-Hop und Interface selbst eintragen |

### Beispiel
PC A will PC B erreichen, dazwischen liegen **R1** und **R2**.

Routing-Tabelle von R1:

| Ziel-Netz | Next-Hop | Interface |
|-----------|----------|-----------|
| 192.168.1.0/24 | direkt verbunden | G0/0 |
| 192.168.2.0/24 | 10.0.0.2 | G0/1 |

### Routing braucht beide Richtungen
Fehlt die Route **zurück**, kommt die Antwort nie an. Der Ping scheitert, obwohl der Hinweg stimmt.

---

## Default-Route

`0.0.0.0/0` passt auf **alle** Ziele und wird nur genutzt, wenn kein genauerer Eintrag passt. Praktisch für den einen Weg nach draussen.

---

## Statisch oder dynamisch?

| | Statisch | Dynamisch |
|--|----------|-----------|
| Eintragen | von Hand | Router tauschen Routen selbst aus |
| Lernen | lernt nichts dazu, macht genau das, was in der Tabelle steht | Routingprotokoll (**RIP, OSPF, BGP**) |
| Vorteil | einfach, volle Kontrolle | bei Ausfall sucht sich das Netz automatisch einen neuen Weg |
| Nachteil | bei grossen Netzen mühsam, bei Ausfall kein Ausweichweg | mehr Rechenleistung, weniger Kontrolle |

> Im Auftrag arbeiten wir mit **statischen Routen**.

---

## Verknüpfungen

→ [[04 - Netzwerkkomponenten]]
→ [[16 - NAT]]
→ [[17 - Analysetools]]
→ [[00 - MOC]]
