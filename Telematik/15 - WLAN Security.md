# WLAN Security

**Fach:** Telematik
**Tags:** #WLAN #WPA2 #WPA3 #SSID #MACFilter

---

## Lernziele

- [ ] Risiken von WLAN nennen
- [ ] Die drei Bausteine SSID, Verschlüsselung, MAC-Filter erklären
- [ ] Warum SSID und MAC-Filter keinen echten Schutz bieten
- [ ] Mindestens WPA2, besser WPA3
- [ ] Tipps zur Absicherung eines WLAN nennen

---

## Warum Security?

Funk ist bequem und offen:

| Vorteile | Risiken |
|----------|---------|
| keine Kabel nötig | jeder in Reichweite kann mithören |
| einfache Gebietsabdeckung | weniger Kontrolle über den Datenverkehr |
| schnelle Entwicklung | Angreifer braucht keinen Zugang zum Gebäude |

---

## Drei Bausteine

| Baustein | Schutz? |
|----------|---------|
| **SSID** | nein – Name des Netzes, wird im Klartext gesendet |
| **Verschlüsselung (WPA2 / WPA3)** | **ja – das ist der eigentliche Schutz** |
| **MAC-Filter** | nur eine Hürde, lässt sich austricksen |

> Nur die Verschlüsselung hält einen Angreifer wirklich draussen.

---

## SSID (Service Set IDentifier)

- Wird im **Klartext** gesendet
- Auch ein **verstecktes Netz** ist mit Werkzeugen sichtbar
- Standardnamen verraten den Hersteller (linksys, tsunami, Wireless …)
- Keine Rückschlüsse zulassen: kein Firmenname, kein Personenname, keine Adresse

---

## Verschlüsselung

Entwicklung von **WEP** über **WPA** zu **WPA2** und **WPA3**.

> **Regel: mindestens WPA2, besser WPA3.** Alles Ältere gilt als gebrochen.

**Anmeldung:** ein Passwort für alle (Pre-Shared Key) oder ein eigenes Login pro Benutzer (Enterprise).

---

## MAC-Filter

- **Idee:** der Access Point kennt eine Liste erlaubter MAC-Adressen, nur bekannte Geräte dürfen rein
- **Aufwand:** jedes neue Gerät muss von Hand eingetragen werden
- **Schwäche:** **MAC-Spoofing** – die Adresse lässt sich per Software fälschen

> Ein MAC-Filter ist eine Hürde, kein Schutz. Er ersetzt keine Verschlüsselung.

---

## Tipps: so sicherst du ein WLAN ab

- **Standard-Passwort ändern** (`admin` gehört gelöscht, am Router und am Access Point)
- **WPA2 oder WPA3** nutzen
- **Reichweite begrenzen** (Sendeleistung und Standort der Antennen)
- **Firmware aktuell halten** (regelmässige Updates)
- **SSID neutral** wählen (kein Hersteller, kein Firmenname)
- **Fernkonfiguration ausschalten** (kein Zugriff aus dem Internet)
- **Gäste trennen** (eigenes Netz, getrennt vom internen LAN)
- **Logs auswerten** (Zugriffe und Angriffsversuche kontrollieren)

---

## Verknüpfungen

→ [[14 - WLAN Grundlagen]]
→ [[05 - Adressierung MAC IPv4 IPv6]]
→ [[00 - MOC]]
