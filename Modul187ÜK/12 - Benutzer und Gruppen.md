# 11 – Benutzer und Gruppen

> **Handlungsziel 8.4:** Konzepte für die Benutzer- und Rechteverwaltung kennen.

---

## Lernziele

- [ ] 8.4 Benutzer- und Rechteverwaltung verstehen (User-ID, Zugriffsrechte, Gruppenmitgliedschaft, Vererbung, Heimverzeichnis)
- [ ] Benutzerkonten-Typen unter Windows 11 kennen
- [ ] SID erklären können
- [ ] Benutzer erstellen und verwalten unter Windows
- [ ] Linux-Konzepte (UID, GID, groups, who, whoami) kennen

---

## Warum individuelle Benutzerkonten?

- **Identifikation + Authentifizierung:** persönlicher Benutzername und Passwort
- Jeder Benutzer hat seine eigene Umgebung:
  - Eigene Dateien / Bibliothek
  - Desktopumgebung, Hintergrundbild
  - Favoritten, Programmeinstellungen
- **Nur diese Person** hat Zugriff auf ihre Daten

---

## Benutzerkonten unter Windows 11

| Typ | Beschreibung |
|-----|-------------|
| **Standardbenutzer** | Normales Arbeitskonto – empfohlen für tägliche Arbeit |
| **Administrator** | Hat auf alles Zugriff |
| **Gastkonto** | Daten werden nach Abmelden gelöscht (meist deaktiviert) |

> **Best Practice:** Im Alltag als **Standardbenutzer** arbeiten, Administrator nur wenn nötig!

---

## SID – Security Identifier

- **SID** = eindeutige Kennung jedes Benutzerkontos
- Wird beim Erstellen eines Kontos neu generiert
- Windows nutzt intern SID (nicht den Benutzernamen) für Berechtigungen
- Anzeigen: `wmic useraccount get name,sid`

---

## Benutzerkontensteuerung (UAC – User Account Control)

- Windows fragt nach, wenn ein Programm dauerhaft Systemänderungen vornehmen will
- Falls Benutzer **keine** Admin-Rechte: Administratorkennwort erforderlich
- Falls Benutzer **ist** Admin: nur Bestätigung nötig
- Aufruf über msconfig oder direkt

---

## Benutzer verwalten (Windows)

- **Computerverwaltung** → Lokale Benutzer und Gruppen
- Neuer Benutzer wird aus "Default User" generiert
- Öffentliche Dateien (für alle Benutzer) → `C:\Users\Public`
- Benutzerprofile: `Erweiterte Systemeinstellungen` (Win+R → `SystemPropertiesAdvanced.exe`)

---

## Benutzer und Gruppen unter Linux

| Befehl | Funktion |
|--------|---------|
| `id [USERNAME]` | UID und GID eines Benutzers anzeigen |
| `groups [USERNAME]` | Gruppenzugehörigkeit anzeigen |
| `who` | Wer ist momentan angemeldet (tty) |
| `whoami` | Aktuell angemeldeter Benutzer |
| `wmic useraccount get name,sid` | SID unter Windows anzeigen |

**Linux-Konzepte:**
- **UID** = User ID (0 = root)
- **GID** = Group ID
- Benutzer können mehreren Gruppen angehören
- Heimverzeichnis: `/home/USERNAME`
- Root-Heimverzeichnis: `/root`

---

## Berechtigungen unter Linux (Kurzübersicht)

```bash
ls -l datei.txt
# -rwxr-xr-- 1 user group 1234 Sep 04 datei.txt
#  ^^^        = Owner-Rechte (r=lesen, w=schreiben, x=ausführen)
#     ^^^     = Group-Rechte
#        ^^^  = Others-Rechte
```

---

## Verknüpfungen

→ [[10 - Datei- und Verzeichnisstruktur]]
→ [[12 - Sicheres Arbeiten als Administrator]]
→ [[00 - MOC]]
