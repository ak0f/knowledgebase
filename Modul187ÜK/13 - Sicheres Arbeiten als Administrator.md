# 12 – Sicheres Arbeiten als Administrator

> **Handlungsziel 8.5:** Massnahmen zum sicheren Arbeiten als Administrator kennen.

---

## Lernziele

- [ ] 8.5 Sicheres Arbeiten als Administrator kennen (Benutzerwechsel, su/sudo/runas, Backup, Dokumentation)
- [ ] Unterschied Benutzer vs. Administrator kennen
- [ ] UAC erläutern können
- [ ] Sicherungspunkte und Backup-Methoden kennen
- [ ] sudo unter Linux richtig einsetzen

---

## Grundprinzip

> **Empfehlung:** Nicht als Administrator arbeiten!
> **Realität:** Oft wird trotzdem als Administrator gearbeitet → Sicherheitsrisiko!

**Warum?**
- Fehler haben grössere Konsequenzen (Systemschäden, Malware-Ausbreitung)
- Malware bekommt automatisch Admin-Rechte

---

## UAC – Benutzerkontensteuerung (Repetition)

**User Account Control:**
- Windows fragt nach, wenn ein Programm dauerhaft Systemänderungen vornehmen darf
- Benutzer **ohne** Admin-Rechte → Administrator-Passwort nötig
- Benutzer **mit** Admin-Rechten → nur Bestätigung

**"Als Administrator ausführen":**
- Explizit mit Admin-Rechten starten
- Nötig für: Installationsprogramme, Systemprogramme, CMD/PowerShell (Admin)

---

## Absichern: Sicherungspunkte / Wiederherstellungspunkte

- **Schnelle Rückkehr** nach Fehlern
- **Ersetzt KEIN** vollständiges Backup!
- In virtuellen Umgebungen **vor grossen Änderungen immer** empfohlen
- Erstellen: Systemsteuerung → Systemschutz → Sicherungspunkt erstellen

---

## Absichern: Backup / Versionen

| Methode | Beschreibung |
|---------|-------------|
| **Dateiversionsverlauf** | Schützt Dokumente (Windows 11) |
| **"Ältere Sicherung"** | Vollständige Systemsicherung (Windows) |
| **Drittanbieter-Software** | z.B. Acronis, Veeam, Clonezilla |
| **Schattenkopien** | Windows Server – Versionsverwaltung von Dateien |

---

## sudo unter Linux

**sudo** = "Als Administrator (root) ausführen"

**Voraussetzungen:**
1. Paket `sudo` ist installiert
2. Benutzer muss in der Gruppe `sudo` sein (oder in `/etc/sudoers`)

```bash
# sudo einrichten (als root)
apt install sudo
adduser user1 sudo

# Anwendung
sudo apt update
sudo apt upgrade
sudo nano /etc/hosts     # Beliebigen Befehl als root ausführen
```

**Faustregel:** Einfach `sudo` vor das eigentliche Kommando setzen!

---

## su vs. sudo vs. runas

| Befehl | OS | Funktion |
|--------|-----|---------|
| `sudo befehl` | Linux | Einen Befehl als root ausführen |
| `su - username` | Linux | Zu anderem Benutzer wechseln |
| `su -` | Linux | Zu root wechseln (braucht root-Passwort) |
| Rechtsklick → "Als Administrator ausführen" | Windows | Programm mit Admin-Rechten starten |
| `runas /user:Administrator cmd` | Windows | CMD als anderer Benutzer starten |

---

## Dokumentation

- Änderungen am System **immer dokumentieren**
- Was wurde geändert? Wann? Warum?
- Ermöglicht Rückverfolgung und Wiederherstellung

---

## Verknüpfungen

→ [[11 - Benutzer und Gruppen]]
→ [[13 - Ressourcen und Ereignisse überwachen]]
→ [[00 - MOC]]
