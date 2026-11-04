# Zahlensysteme (Exkurs)

**Fach:** Telematik
**Tags:** #Binär #Hexadezimal #Dezimal #Umrechnen

---

## Lernziele

- [ ] Dezimal, binär, hexadezimal unterscheiden
- [ ] Binär → Dezimal umrechnen (addieren)
- [ ] Dezimal → Binär umrechnen (subtrahieren)
- [ ] Hexadezimal ↔ Binär umrechnen

---

## Drei Zahlensysteme

| System | Ziffern | Wofür |
|--------|---------|-------|
| **Dezimal** | 0–9 | Alltag |
| **Binär** | 0 und 1 | Sprache des Computers |
| **Hexadezimal** | 0–9 und A–F | Kurzschreibweise für Bits |

**Grundidee:** jede Stelle hat einen Wert, nach links wird jede Stelle um die **Basis** wertvoller.

- Dezimal (Basis 10): 1000 · 100 · 10 · 1
- Binär (Basis 2): 8 · 4 · 2 · 1 (bei 8 Bits: 128 · 64 · 32 · 16 · 8 · 4 · 2 · 1)

---

## Binär → Dezimal: einfach addieren

Beispiel `100111`

| 32 | 16 | 8 | 4 | 2 | 1 |
|----|----|---|---|---|---|
| 1 | 0 | 0 | 1 | 1 | 1 |

`32 + 4 + 2 + 1 = 39`

Nur die Stellenwerte zählen, unter denen eine **1** steht.

---

## Dezimal → Binär: von links subtrahieren

Beispiel `39`

| 32 | 16 | 8 | 4 | 2 | 1 |
|----|----|---|---|---|---|
| 1 | 0 | 0 | 1 | 1 | 1 |

- Passt der Stellenwert in die Zahl? → **1** schreiben und abziehen
- Passt er nicht? → **0** schreiben und weiter nach rechts

`39 − 32 = 7` → `7 − 4 = 3` → `3 − 2 = 1` → `1 − 1 = 0`

---

## Hexadezimal

- 16 Ziffern: `0 1 2 3 4 5 6 7 8 9 A B C D E F` (**A = 10**, **F = 15**)
- **Eine Hex-Ziffer = vier Bits** → darum lassen sich MAC- und IPv6-Adressen so kurz schreiben

### Hex → Binär: Ziffer für Ziffer

| F | E | 3 | B |
|---|---|---|---|
| 1111 | 1110 | 0011 | 1011 |

`0xFE3B = 1111 1110 0011 1011` – kein Rechnen nötig.

---

## Verknüpfungen

→ [[05 - Adressierung MAC IPv4 IPv6]]
→ [[08 - Subnetting]]
→ [[00 - MOC]]
