# Befehle Cheatsheet

> Alle wichtigen Linux-Befehle auf einen Blick.

---

## Navigation & Dateisystem

```bash
pwd                         # Aktuelles Verzeichnis anzeigen
ls                          # Verzeichnis auflisten
ls -l                       # Ausführliche Liste
ls -la                      # Mit versteckten Dateien
cd /pfad/zum/verzeichnis    # Verzeichnis wechseln
cd ..                       # Ein Verzeichnis höher
cd ~                        # Home-Verzeichnis
```

---

## Dateien verwalten

```bash
cp quelle ziel              # Datei kopieren
cp -r quelle ziel           # Ordner kopieren
mv quelle ziel              # Verschieben / Umbenennen
cat datei.txt               # Dateiinhalt anzeigen
grep "suchbegriff" datei    # In Datei suchen
grep -i "suche" datei       # Gross-/Kleinschreibung ignorieren
grep -r "suche" /pfad       # Rekursiv suchen
```

---

## Rechte & Eigentümer

```bash
chmod 755 datei             # Oktal setzen
chmod 644 datei             # Standard Datei
chmod -R 755 /pfad          # Rekursiv
chmod u+x datei             # Ausführen für Eigentümer hinzufügen
chmod o-w datei             # Schreibrecht für Andere entfernen
chown benutzer datei        # Eigentümer ändern
chown benutzer:gruppe datei # Eigentümer und Gruppe ändern
```

**Oktal Merkhilfe:**
```
r=4  w=2  x=1
rwx r-x r-x  = 7 5 5
rw- r-- r--  = 6 4 4
```

---

## Benutzer & Gruppen

```bash
id [USER]                   # UID, GID, Gruppen
who                         # Eingeloggte Benutzer
whoami                      # Aktueller Benutzer
groups [USER]               # Gruppen eines Benutzers

useradd benutzername        # Benutzer anlegen (minimal)
adduser benutzername        # Benutzer anlegen (interaktiv)
usermod -aG gruppe user     # Zu Gruppe hinzufügen
passwd [USER]               # Passwort setzen/ändern
userdel benutzername        # Benutzer löschen
deluser --remove-home user  # Mit Home löschen

addgroup gruppenname        # Gruppe erstellen
delgroup gruppenname        # Gruppe löschen

su benutzername             # Benutzer wechseln
```

---

## System & Admin

```bash
sudo befehl                 # Mit Root-Rechten ausführen
echo $SHELL                 # Aktuelle Shell anzeigen
man befehl                  # Handbuch
befehl --help               # Kurzinfo
apropos stichwort           # Handbuch durchsuchen
```

---

## Mount / Datenträger

```bash
sudo mount /dev/sdc1 /mnt  # Datenträger mounten
sudo mount                  # Gemountete Geräte anzeigen
df -h                       # Festplattenplatz anzeigen
```

---

## SSH

```bash
ssh user@ip-adresse         # SSH-Verbindung aufbauen
ssh akif@192.168.1.100      # Beispiel
```

---

## Umleitung & Pipe

```bash
befehl > datei              # Ausgabe in Datei (überschreiben)
befehl >> datei             # Ausgabe anhängen
befehl1 | befehl2           # Ausgabe weiterleiten
cat datei | grep "suche"    # Pipe-Beispiel
```

---

## Tastaturkürzel

| Kürzel | Aktion |
|--------|--------|
| `Ctrl+C` | Abbruch |
| `Ctrl+A` | Zeilenanfang |
| `Ctrl+E` | Zeilenende |
| `Ctrl+R` | Verlauf durchsuchen |
| `TAB` | Autovervollständigung |
| `↑ / ↓` | Befehlsverlauf |

---

## /etc/passwd Format

```
tux : x : 1000 : 1000 : Pingu,,, : /home/tux : /bin/bash
 1    2     3      4       5           6           7
```

1. Benutzername
2. Passwort (x = in /etc/shadow)
3. UID
4. GID
5. Kommentar
6. Home-Verzeichnis
7. Shell

---

## Prozesse beenden (Linux)

```bash
kill PID              # Prozess freundlich beenden
kill -9 PID           # Prozess erzwungen beenden
killall programmname  # Prozess nach Name beenden
```

---

## Logs (Linux)

```bash
journalctl              # Alle Logs anzeigen
journalctl -p err       # Nur Fehler
journalctl -f           # Live-Ansicht
journalctl -b           # Seit letztem Boot
```

**Log-Dateien:** `/var/log/syslog` · `/var/log/auth.log`

---

## Systeminfo (Linux)

```bash
top                     # Prozesse & Ressourcen
htop                    # Benutzerfreundlicher top
free -h                 # RAM-Auslastung
uname -a                # Systeminformationen
```

---

## Windows Monitoring

```
Ctrl+Shift+Esc          → Task-Manager
Win+R → eventvwr.msc    → Ereignisanzeige
Win+R → msinfo32        → Systeminformationen
```

---

## Verknüpfungen

→ [[00 - MOC]]
→ [[Prüfungsvorbereitung]]
