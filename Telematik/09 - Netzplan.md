# Netzplan

**Fach:** Telematik
**Tags:** #Netzplan #Symbole #Namenskonzept #VLAN

---

## Lernziele

- [ ] Wozu ein Netzplan dient
- [ ] Schematischen und geographischen Netzplan unterscheiden
- [ ] Standardsymbole kennen
- [ ] Namenskonzept anwenden
- [ ] Pflichtangaben auf jedem Plan nennen

---

## Wozu?

Das Versteckte **sichtbar machen**: Funktionen der Geräte, Verbindungen, Standorte. Zusammenhänge zeigen: wer ist womit verbunden, wie funktionieren die Geräte miteinander?

---

## Zwei Arten

| | Schematischer Netzplan | Geographischer Netzplan |
|--|------------------------|-------------------------|
| Zeigt | **Technik und Funktion** (Standort unwichtig) | **Standort** (welches Gerät in welchem Raum) |
| Nutzen | technische Übersicht, Funktion des Netzes | genauer Standort, Ort der Geräte |
| Verwendung | Planung des Netzes, Analyse des Fehlers, Konfiguration | Support, Hardware, Behebung des Fehlers |

---

## Standardsymbole

Immer die gleichen verwenden: **Router, Switch, Bridge, Firewall, Hub, Router mit Firewall, Wireless, Netz**.
Jedes Gerät hat sein eigenes Icon: PC, Switch, Router, Server, Access Point.

---

## Minimalregeln beim Zeichnen

1. Gerade Linien verwenden
2. Kreuzungen vermeiden
3. Übersichtlich

---

## Namenskonzept (verbindlich)

| Typ | Präfix | Nummerierung | Beispiel |
|-----|--------|--------------|----------|
| Server | `s` | ohne führende Null, Start 1 | `s1` |
| Gigabit Ethernet Adapter | `ge` | ohne führende Null, Start 0 | `ge0` |
| Switch Layer 2 | `sw` | eine führende Null, Start 1 | `sw01` |
| Switch Layer 3 | `l3sw` | eine führende Null, Start 1 | `l3sw01` |

**Immer klein geschrieben und alphanumerisch.** Gleiche Namen im Netzplan und auf dem Gerät.

---

## Pflicht auf jedem Plan

1. **Netz als Ganzes:** Netzadresse und Subnetzmaske angeschrieben, z. B. `192.168.1.0/24`
2. **Vollständige Angaben pro Gerät:** Gerätename, IP mit Subnetzmaske (oder MAC, wenn es keine IP hat), Funktion und Betriebssystem
3. **Richtiges Icon**
4. **VLANs als eigene Netze:** jedes VLAN mit eigener Netzadresse, nicht nur als Nummer am Switch

---

## Verknüpfungen

→ [[04 - Netzwerkkomponenten]]
→ [[08 - Subnetting]]
→ [[00 - MOC]]
