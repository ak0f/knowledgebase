# Prüfungsvorbereitung – Alle Lernziele

> Hake jedes Lernziel ab wenn du es beherrschst.

---

## Modul 1 – Software und Hardware

- [ ] Hardware-Komponenten benennen: CPU, RAM, HDD, SSD, GPU, PSU
- [x] Unterschied Hardware / Software erklären
- [x] Was macht ein Betriebssystem?
- [x] OS-Familien kennen (Unix/Darwin, Linux, Windows NT)

---

## Modul 2 – Betriebssysteme

- [ ] Unix – Entstehung (1969, Bell Labs), Merkmale, Anwendungsfälle, 2 Beispiele
- [ ] Linux – Entstehung (Torvalds, GNU), Merkmale, Anwendungsfälle, 2 Beispiele
- [ ] Windows – Microsoft, proprietär, Anwendungsfälle, 2 Beispiele
- [ ] Unterschiede Unix / Linux / Windows erklären

---

## Modul 3 – Linux Kennenlernen

- [ ] Was ist eine Shell? Typen nennen (bash, sh, zsh...)
- [ ] Prompt-Aufbau erklären: `user@hostname:verzeichnis$`
- [ ] Befehlsstruktur: `kommando [optionen] [argumente]`
- [ ] `ls`, `cd`, `pwd`, `mv`, `cp`, `cat`, `grep` anwenden
- [ ] Wildcards: `*`, `?`, `[1-4]`
- [ ] Umleitung `>`, `>>` und Pipe `|` erklären

---

## Modul 4 – Datei- und Verzeichnisstruktur

- [ ] Absoluter Pfad (beginnt mit `/`) vs. relativer Pfad (`.` und `..`)
- [ ] Linux-Verzeichnisse: `/`, `/bin`, `/etc`, `/home`, `/media`, `/mnt`
- [ ] Windows-Verzeichnisse: `C:\`, `C:\Users\`, `C:\Windows\System32\`, `C:\Program Files\`
- [ ] Mountpoint erklären
- [ ] `sudo mount /dev/sdc1 /mnt` anwenden
- [ ] `df -h` lesen

---

## Modul 5 – Dateisystemrechte

- [ ] `ls -l` Ausgabe vollständig lesen
- [ ] Dateityp erkennen: `d` = Verzeichnis, `-` = Datei, `l` = Link
- [ ] Rechte rwx für Owner / Group / Others lesen
- [ ] Oktalwerte berechnen: r=4, w=2, x=1
- [ ] `chmod 755 datei` – oktal setzen
- [ ] `chmod u+x datei` – symbolisch ändern
- [ ] `chmod -R 755 /pfad` – rekursiv
- [ ] `chown benutzer:gruppe datei`

---

## Modul 6 – Benutzer und Gruppen

- [ ] /etc/passwd Felder erklären (7 Felder)
- [ ] Root = UID 0, GID 0
- [ ] `id`, `who`, `whoami`, `groups` anwenden
- [ ] `useradd` vs `adduser` – Unterschied erklären
- [ ] `usermod -aG gruppe benutzer` (Gruppe hinzufügen)
- [ ] `passwd [USER]` – Passwort setzen
- [ ] `userdel` vs `deluser --remove-home`
- [ ] `addgroup` / `delgroup`
- [ ] `su benutzername` – Benutzer wechseln

---

## Modul 7 – Administrationsrechte

- [ ] `sudo befehl` – in Linux erklären und anwenden
- [ ] "Als Administrator ausführen" in Windows beschreiben
- [ ] Principle of Least Privilege erklären
- [ ] 3 Risiken von dauerhaften Admin-Rechten nennen

---

## Modul 8 – SSH

- [ ] SSH = Secure Shell – Bedeutung erklären
- [ ] Wofür wird SSH genutzt? (3 Anwendungsfälle)
- [ ] SSH-Verbindungsablauf beschreiben
- [ ] `ssh user@ip` Befehl anwenden
- [ ] BbcNet → SSH → EduNet erklären

---

## Modul 10 – Bootvorgang und BIOS/UEFI

- [ ] Bootvorgang in 4 Phasen erklären: Firmware → POST → Bootloader → OS
- [ ] Unterschied BIOS (seit 1981, nur Text, max. 2 TB) vs. UEFI (seit 2010, grafisch, Secure Boot)
- [ ] POST erklären: was wird geprüft? (CPU, RAM, GPU, Festplatten)
- [ ] Bootreihenfolge nennen (USB → HDD → Netzwerk)
- [ ] UEFI aufrufen: F2 / F10 / F12 / DEL; EduNet OptiPlex: F2 (UEFI), F12 (One-Time-Boot)
- [ ] Bootloader erklären: Windows = Windows Boot Manager, Linux = GRUB
- [ ] Secure Boot erklären (digitale Signatur, verhindert Schadsoftware)
- [ ] Häufige Probleme: "No bootable device", Pieptöne beim Start

---

## Modul 11 – Systemüberwachung und Troubleshooting

- [ ] Task-Manager öffnen (Ctrl+Shift+Esc) und Tabs erklären
- [ ] Prozess im Task-Manager beenden (Task beenden)
- [ ] Ereignisanzeige öffnen (Win+R → eventvwr.msc), Protokolltypen nennen
- [ ] `top` / `htop` starten und lesen (PID, %CPU, %MEM, Load Average)
- [ ] Prozess mit `kill PID`, `kill -9 PID`, `killall` beenden
- [ ] `journalctl`, `journalctl -p err`, `journalctl -f`, `journalctl -b`
- [ ] 5-Schritte-Methode erklären: Problem → Kategorie → Infos → Test → Dokumentation
- [ ] Typische Fehler zuordnen: CPU voll → htop, RAM voll → free -h, HDD voll → df -h

---

## Modul 9 – EduNet

- [ ] EduNet = separates Netz vom BbcNet
- [ ] Erlaubt / Verboten im EduNet nennen
- [ ] Aufbau / Setup beschreiben

---

## Schnell-Wiederholung: Wichtigste Befehle

```bash
# Dateisystem
ls -l          chmod 755 datei     chown user:gruppe datei

# Benutzer
id             useradd / adduser   usermod -aG gruppe user
passwd user    userdel / deluser   su benutzername

# Navigation
pwd            cd /pfad            ls -la

# System
sudo befehl    mount /dev/sdc1 /mnt    df -h    echo $SHELL
```

---

## Verknüpfungen

→ [[00 - MOC]]
→ [[Befehle-Cheatsheet]]
