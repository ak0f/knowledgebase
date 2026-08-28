# Benutzer und Gruppen

**Modul:** Benutzer und Gruppen (220)
**Tags:** #Linux #Benutzer #Gruppen #useradd #passwd

---

## Lernziele

- [ ] /etc/passwd alle 7 Felder erklären
- [ ] Root = UID 0, GID 0 erklären
- [ ] `id`, `who`, `whoami`, `groups` anwenden
- [ ] Unterschied `useradd` vs `adduser` erklären
- [ ] `usermod -aG gruppe benutzer` (Gruppe hinzufügen)
- [ ] `passwd [USER]` – Passwort setzen
- [ ] `userdel` vs `deluser --remove-home` unterscheiden
- [ ] `addgroup` / `delgroup` anwenden
- [ ] `su benutzername` – Benutzer wechseln

---

## /etc/passwd Format

```
tux:x:1000:1000:Pingu,,,:/home/tux:/bin/bash
```

| Feld | Inhalt | Beispiel |
|------|--------|---------|
| 1 | Benutzername | `tux` |
| 2 | Passwort (x = in /etc/shadow) | `x` |
| 3 | UID (User ID) | `1000` |
| 4 | GID (Group ID) | `1000` |
| 5 | Kommentar / GECOS | `Pingu,,,` |
| 6 | Home-Verzeichnis | `/home/tux` |
| 7 | Login-Shell | `/bin/bash` |

**Root:**
- UID = 0, GID = 0
- Uneingeschränkte Rechte

---

## Benutzerinformationen anzeigen

```bash
id [USERNAME]       # UID, GID, Gruppen anzeigen
who                 # Wer ist eingeloggt?
whoami              # Aktueller Benutzername
groups [USERNAME]   # Gruppen eines Benutzers
```

---

## useradd vs adduser

| | `useradd` | `adduser` |
|--|-----------|-----------|
| Art | Minimal, low-level | Interaktiv, high-level |
| Home | Wird NICHT erstellt | Wird erstellt (aus /etc/skel) |
| Passwort | Wird NICHT gesetzt | Wird abgefragt |
| Verwendung | Skripte | Manuell / interaktiv |

---

## Benutzer anlegen

```bash
# Einfach (kein Home, kein Passwort)
useradd benutzername

# Interaktiv (mit Home, Passwort etc.)
adduser benutzername

# Mit Optionen
sudo adduser beispiel_benutzer \
  --ingroup benutzer \
  --home /var/beispiel_benutzer \
  --shell /bin/sh
```

---

## Benutzer modifizieren

```bash
# Zu Gruppen hinzufügen (-a = append, WICHTIG!)
usermod -aG haus,boot beispiel_benutzer

# Passwort ändern
passwd [USERNAME]
```

> **Achtung:** ohne `-a` werden alle bisherigen Gruppen ersetzt!

---

## Benutzer löschen

```bash
# Minimal (nur /etc/passwd und /etc/shadow)
userdel benutzername

# Mit Home-Verzeichnis und Backup
deluser --remove-home --backup benutzername
```

---

## Gruppen verwalten

```bash
addgroup gruppenname          # Gruppe erstellen
delgroup gruppenname          # Gruppe löschen
gpasswd gruppenname           # Gruppenpasswort setzen
```

---

## Benutzer wechseln

```bash
su benutzername               # Zu Benutzer wechseln
su -                          # Zu Root wechseln (mit Environment)
```

---

## Verknüpfungen

→ [[05 - Dateisystemrechte]]
→ [[07 - Administrationsrechte]]
→ [[Befehle-Cheatsheet]]
