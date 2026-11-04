# Schichtenmodelle

**Fach:** Telematik
**Tags:** #OSI #TCPIP #Encapsulation #Layer

---

## Lernziele

- [ ] Erklären warum man Schichtenmodelle verwendet (Abstraktion)
- [ ] Die 7 OSI-Schichten in der richtigen Reihenfolge nennen
- [ ] Aufgaben der OSI-Schichten beschreiben
- [ ] TCP/IP-Modell (4 Schichten) dem OSI-Modell zuordnen
- [ ] Encapsulation / Decapsulation erklären

---

## Grundidee

- **Abstrahieren:** aus dem Besonderen das Allgemeine entnehmen – vereinfachen, ohne falsch zu werden
- Schichtenmodelle abstrahieren komplexe Vorgänge, machen Sachverhalte einfach vermittelbar, man kann richtige Aussagen machen ohne jedes Detail zu kennen

### Beispiel Brief
- Hohe Layer: Absender schreibt, verpackt, wirft in den Briefkasten / Empfänger holt und liest
- Mittlere Layer: Pöstler und Postbüro, Träger (Lastwagen)
- Tiefe Layer: der Lastwagen selbst = das eigentliche Medium

> **Schlüssel = die Schnittstelle (Briefkasten).** Eine Schicht darf sich ändern, solange die Schnittstelle bleibt.

---

## ISO/OSI – 7 Schichten

| # | Schicht (DE) | Englisch | Aufgabe |
|---|--------------|----------|---------|
| 7 | Anwendung | Application | stellt Anwendungen und Usern Funktionalität/Services zur Verfügung |
| 6 | Darstellung | Presentation | standardisiert Datenstrukturen: Kodierung, Kompression, Kryptographie |
| 5 | Sitzung | Session | kontrolliert den Nachrichtenaustausch, regelt die Richtung der Verbindung |
| 4 | Transport | Transport | Daten werden in **Segmente** unterteilt |
| 3 | Vermittlung | Network | Pakete werden in die richtige Richtung **geroutet** |
| 2 | Sicherung | Data Link | Daten in kleinere **Frames** mit Prüfsummen |
| 1 | Bitübertragung | Physical | Daten als **Bits** ans Medium übergeben |

### Eselsbrücken
- **Alle deutschen Studenten trinken verschiedene Sorten Bier** (7 → 1)
- **Alle Priester saufen Tequila nach der Predigt** (7 → 1)

### Paketversand-Vergleich

| Layer 7–5 | Layer 4 | Layer 3 | Layer 2 | Layer 1 |
|-----------|---------|---------|---------|---------|
| Produkt entsteht | in Kisten verpacken, Empfangsbestätigung? | Adresse draufschreiben | Inventarliste beilegen | ab die Post |

---

## TCP/IP – 4 Schichten

| TCP/IP | OSI |
|--------|-----|
| **Anwendungsschicht** | 7 Anwendung, 6 Darstellung, 5 Sitzung |
| **Transportschicht** | 4 Transport |
| **Internetschicht** | 3 Vermittlung |
| **Netzzugangsschicht** | 2 Sicherung, 1 Bitübertragung |

Gröber, aber für Netzwerkprobleme meist ausreichend.

---

## Encapsulation

- Jede Schicht packt das Ganze neu ein und hängt ihren **Header** davor
- Auf der Verpackung steht nur, was diese Schicht braucht → keine Schicht muss verstehen, was drin ist

| Ebene | Name | Aufbau |
|-------|------|--------|
| Daten | Daten | Daten |
| 4 | **Segment** | TCP + Daten |
| 3 | **Paket** | IP + TCP + Daten |
| 2 | **Frame** | Eth + IP + TCP + Daten |

Beim Empfänger wird von aussen nach innen wieder ausgepackt → **Decapsulation**.

---

## Verknüpfungen

→ [[04 - Netzwerkkomponenten]]
→ [[10 - Protokolle]]
→ [[17 - Analysetools]]
→ [[00 - MOC]]
