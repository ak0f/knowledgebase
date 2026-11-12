# Vorgehen: Probleme lösen

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Problemlösen #Teile-und-herrsche #FailFast #Methodik

---

## Lernziele

- [ ] Ein Problem systematisch analysieren
- [ ] Probleme visualisieren
- [ ] Teile und Herrsche mit Abstraktionsebenen anwenden
- [ ] Gezielt im Internet recherchieren
- [ ] Fail Fast und die Rule of Ten erklären
- [ ] Wissen, wann man Hilfe holt

> Der Job von Informatiker:innen in zwei Worten: **Probleme lösen**.

---

## 1. Ein Problem angehen

Erst vollständig verstehen. Analysieren:

| Frage | Inhalt |
|-------|--------|
| **Ursache** | Warum tritt das Problem auf? |
| **Zeitpunkt und Häufigkeit** | Wann, wie oft, unter welchen Bedingungen? |
| **Stakeholder-Anforderungen** | Was erwarten Betroffene? |
| **Rahmenbedingungen** | technisch, organisatorisch, zeitlich |
| **Auswirkungen** | Wer ist betroffen? Risiko bei Nichtstun? |
| **Bestehende Ansätze** | Workarounds? Warum reichen sie nicht? |
| **Ziel und Erfolgskriterien** | Woran messen wir die Lösung? |

---

## 2. Visualisieren

Probleme mit einfachen Skizzen greifbar machen (Video "Problem Solving With Simple Pictures" von Dan Roam).

- **Komplexität reduzieren** – Wesentliches vom Unwesentlichen trennen
- **Gemeinsames Verständnis** – alle schauen auf dasselbe Bild
- **Kreativität** – Ideen entstehen beim Zeichnen
- **Effiziente Kommunikation** – Bild sagt mehr als langer Text

---

## 3. Teile und Herrsche

*Divide et impera*: grosse Aufgaben in handhabbare Teilaufgaben zerlegen.

**Vorteile:** Überblick behalten, Fehlerbereich eingrenzen, nicht im Detail versinken.

### Single Level of Abstraction

Alle Teilaufgaben einer Ebene haben **denselben Detailgrad**. "Wohnzimmer einrichten" und "Büro einrichten" passen zusammen, "Dübel mit Leim befestigen" gehört auf eine tiefere Ebene.

**Beispiel Kaffee servieren:**

| Ebene 1 | Ebene 2 |
|---------|---------|
| 1. Kaffee wählen | |
| 2. Geld entgegennehmen | 2.1 Geld überprüfen, 2.2 Einkassieren |
| 3. Kaffee vorbereiten | 3.1 Glas vorbereiten, 3.2 Maschine einstellen, 3.3 Kaffee ins Glas füllen |
| 4. Kaffee servieren | |

**Vorgehen:** Gesamtaufgabe definieren → Hauptschritte → bei Bedarf weiter unterteilen → am Ende alles zusammenfügen.

---

## 4. Googlen, Bingen, Recherchieren

- **Präzise Fragen:** nicht "Mein Code funktioniert nicht", sondern "In Python 3.10 wirft meine Funktion X bei Y einen TypeError: erwartet int, erhalten str"
- **Gezielt suchen:** relevante Schlüsselwörter + Programmiersprache
- **Kritisch prüfen:** Wer steckt dahinter? Passt es zu meinem Framework? Ist der Code sicher? Testen!
- **Version und Datum beachten:** Beispiel von 2015 kann heute scheitern
- **Feedback nutzen:** Upvotes, Kommentare, GitHub-Issues lesen
- **Quelle angeben:** `# Adapted from https://...`

**KI am Anfang nicht ideal:** Studien zeigen, dass Code-Generierungstools zu eingeschränktem Verständnis der Grundlagen führen können. Erst in einigen Monaten sinnvoll und gezielt einsetzen.

---

## 5. Fail Fast

> Je früher ein Fehler entdeckt wird, desto schneller und günstiger ist er zu beheben.

**Rule of Ten:**

| Phase | Aufwand pro Fehler |
|-------|--------------------|
| Entwicklung | 1x |
| Produktion / Qualitätsmanagement | 10x |
| Beim Kunden | 100x |

**In der Praxis:**

- Annahmen hinterfragen und im Code dokumentieren
- **Unit-Tests** schreiben und nach jeder Änderung ausführen
- Änderungen **klein und fokussiert** halten
- Sobald fehlerfrei: sofort **committen**

**Vorteile:** weniger Bugs, stabiler und wartbarer Code, weniger Debugging-Zeit, mehr Motivation.

---

## 6. Hilfe in Anspruch nehmen

Informatik ist **Teamsport**.

**Ablauf:** Problemlöseverhalten anwenden → gelöst? Ja = fertig. Nein → alleine in nützlicher Frist lösbar? Nein → **Hilfe holen**.

**Beim Fragen beachten:**

- Kontext geben (woran arbeitest du?)
- Problem so konkret wie möglich benennen
- Auflisten, was du schon versucht hast
- Balance zwischen Fragen und selbstständigem Weiterarbeiten
- Probleme sammeln, wenn der Coach nicht da ist
- Grosse Änderungen kurz abklären

---

## Verknüpfungen

→ [[18 - Debugging]]
→ [[19 - Entwickler-Tests]]
→ [[21 - Einstieg UML]]
