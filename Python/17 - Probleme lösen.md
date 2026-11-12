# Probleme lösen

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Problemlösen #Teile-und-herrsche #FailFast

> Der Job in zwei Worten: Probleme lösen.

---

## 1. Problem verstehen

| Frage | Inhalt |
|-------|--------|
| Ursache | Warum tritt es auf? |
| Zeitpunkt / Häufigkeit | Wann, wie oft? |
| Stakeholder | Was erwarten die Betroffenen? |
| Rahmenbedingungen | technisch, organisatorisch, zeitlich |
| Auswirkungen | Wer ist betroffen? Risiko? |
| Bestehende Ansätze | Workarounds? Warum reichen sie nicht? |
| Ziel | Woran messe ich den Erfolg? |

## 2. Visualisieren

Mit einfachen Skizzen (Dan Roam, *Problem Solving With Simple Pictures*): weniger Komplexität, gemeinsames Verständnis, mehr Ideen, schnellere Kommunikation.

---

## 3. Teile und Herrsche

Grosse Aufgabe in kleine Teilaufgaben zerlegen. So behalte ich den Überblick und finde Fehler schneller.

**Single Level of Abstraction:** Alle Teilaufgaben einer Ebene haben denselben Detailgrad. "Büro einrichten" passt zu "Wohnzimmer einrichten", "Dübel mit Leim befestigen" ist eine Ebene tiefer.

| Ebene 1 | Ebene 2 |
|---------|---------|
| Kaffee wählen | |
| Geld entgegennehmen | prüfen, einkassieren |
| Kaffee vorbereiten | Glas vorbereiten, Maschine einstellen, einfüllen |
| Kaffee servieren | |

---

## 4. Recherchieren

- **Präzise fragen:** nicht "Code geht nicht", sondern "Python 3.10, Funktion X wirft TypeError: erwartet int, erhalten str"
- **Kritisch prüfen:** Wer steckt dahinter? Ist der Code sicher? Testen!
- **Version und Datum** beachten (Beispiele von 2015 gehen evtl. nicht mehr)
- Upvotes, Kommentare, Issues lesen
- **Quelle angeben:** `# Adapted from https://...`
- **KI am Anfang nicht ideal:** Sie verhindert, dass ich die Grundlagen selber verstehe

---

## 5. Fail Fast

Fehler früh finden, dann sind sie billiger.

| Phase | Aufwand |
|-------|---------|
| Entwicklung | 1x |
| Produktion | 10x |
| Beim Kunden | 100x |

**Rule of Ten.** In der Praxis: Annahmen im Code festhalten, **Unit-Tests** nach jeder Änderung, kleine Änderungen, bei fehlerfreiem Stand sofort **committen**.

---

## 6. Hilfe holen

Informatik ist Teamsport. Wenn ich in nützlicher Zeit nicht weiterkomme, frage ich den Coach.

- Kontext geben, Problem konkret benennen
- sagen, was ich schon probiert habe
- Fragen sammeln, wenn der Coach nicht da ist
- grosse Änderungen kurz absprechen

---

→ [[18 - Debugging]] · [[19 - Entwickler-Tests]] · [[21 - Einstieg UML]]
