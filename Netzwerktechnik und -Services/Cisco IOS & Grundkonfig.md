# Cisco IOS & Grundkonfig – Lab

Router 2901 in Packet Tracer, PC über Konsolenkabel verbunden. Terminal auf dem PC unter Desktop → Terminal.

## Aufgabe 1 – Softwareinformationen anzeigen

- **Befehl:** `show version`
- **IOS-Version:** 15.1(4)

## Aufgabe 2 – Die integrierte Hilfe kennenlernen

- **Was wird angezeigt?** Mit `?` werden alle Befehle angezeigt, die im aktuellen Modus möglich sind.
- **Wofür ist das hilfreich?** Es hilft bei Befehlen, die man vergessen hat. Man kann auch einen Teil eines Befehls eingeben und dann `?` drücken (z. B. `show ?`), dann sieht man, wie es weitergeht.

## Aufgabe 3 – In den privilegierten Modus wechseln

- **Befehl:** `enable`
- **Wie verändert sich die Eingabeaufforderung?** Aus `Router>` wird `Router#`.

## Aufgabe 4 – Konfigurationsmodus öffnen

- **Befehl:** `configure terminal` (oder `conf t`)
- **Welche Änderung erkennst du an der Eingabeaufforderung?** Aus `Router#` wird `Router(config)#`.

## Aufgabe 5 – Routername ändern

- **Befehl:** `hostname Bbc-Router`
- Dieser Befehl muss im Konfigurationsmodus `Router(config)#` eingegeben werden.
- Danach heisst die Eingabeaufforderung `Bbc-Router(config)#`.

## Aufgabe 6 – Passwort für den privilegierten Modus setzen

- **Befehl:** `enable secret Bbc-PE`
- **Weshalb sollte der privilegierte Modus geschützt werden?** Dort kann man die ganze Konfiguration ansehen und ändern. Ohne Passwort könnte jeder, der am Gerät ist, alles verstellen.
- **Wo könnte ein solches Passwort sinnvoll sein?** Auf allen Routern und Switches, vor allem dort, wo mehrere Personen oder fremde Personen an das Gerät kommen.

## Aufgabe 7 – Konfiguration speichern

- Zuerst muss ich aus dem Konfigurationsmodus zurück in den privilegierten Modus: `end` (oder `exit`).
- **Befehl:** `copy running-config startup-config`
- **Warum ist das Speichern wichtig?** Die `running-config` liegt im RAM. Beim Neustart gehen die Änderungen verloren. Die `startup-config` bleibt gespeichert und wird beim Start geladen.

## Aufgabe 8 – Konfiguration kontrollieren

- **Gerätename:** `show running-config` → Zeile `hostname Bbc-Router`
- **Passwort:** `show running-config` → Zeile `enable secret 5 ...` (das Passwort ist verschlüsselt und nicht im Klartext sichtbar)
- **Gespeicherte Konfiguration:** `show startup-config` → hier stehen dieselben Einträge, wenn ich gespeichert habe

---

## Wichtigste Befehle

| Befehl | Bedeutung |
|--------|-----------|
| `show version` | IOS-Version und Geräteinfos |
| `?` | Hilfe, zeigt die möglichen Befehle |
| `enable` | in den privilegierten Modus (`#`) |
| `configure terminal` | in den Konfigurationsmodus |
| `hostname <Name>` | Gerätename ändern |
| `enable secret <Passwort>` | Passwort für den privilegierten Modus |
| `end` / `exit` | zurück in den privilegierten Modus / eine Ebene zurück |
| `copy running-config startup-config` | Konfiguration speichern |
| `show running-config` | aktuelle Konfiguration anzeigen |
| `show startup-config` | gespeicherte Konfiguration anzeigen |

---

## Transferprojekt (01_IOS)

Nur das, was im Lab vorkommt:

- [ ] `hostname` auf allen Routern und Switches
- [ ] `enable secret` auf allen Routern und Switches
- [ ] Konfiguration speichern (`copy running-config startup-config`)
- [ ] Kontrolle mit `show running-config`
- [ ] Datei als `01_IOS_Name.pkt` speichern
- [ ] Doku nachführen (Namenskonzept, Geräteliste, Kapitel 6.5, Kapitel 7)
