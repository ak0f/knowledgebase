# Administrationsrechte

**Modul:** Administrationsrechte – sudo / runas (125)
**Tags:** #Linux #Windows #sudo #runas #Sicherheit

---

## Lernziele

- [ ] sudo in Linux korrekt anwenden
- [ ] "Als Administrator ausführen" in Windows anwenden
- [ ] Principle of Least Privilege erklären
- [ ] **3 Risiken** von dauerhaften Admin-Rechten nennen

---

## Linux – sudo

```bash
sudo <befehl>
```

- Fragt nach dem **eigenen Benutzerpasswort**
- Führt Befehl mit **Root-Rechten** aus
- Benutzer muss in der `sudo`-Gruppe sein

**Beispiele:**
```bash
sudo apt update
sudo adduser neuerbenutzer
sudo mount /dev/sdc1 /mnt
sudo chmod 755 /etc/config
```

---

## Windows – Als Administrator ausführen

**Methode 1 – GUI:**
`Shift + Rechtsklick` → „Als Administrator ausführen"

**Methode 2 – PowerShell:**
```powershell
Start-Process cmd.exe -Verb RunAs
```

---

## Principle of Least Privilege

> Jeder Benutzer und Prozess sollte **nur die minimal notwendigen Rechte** haben.

**Warum?**
- Weniger Schaden bei Fehlern
- Kleinere Angriffsfläche
- Malware hat weniger Rechte

---

## Risiken von dauerhaften Admin-Rechten

| Risiko | Erklärung |
|--------|-----------|
| **Malware** | Schadsoftware läuft mit vollen Rechten |
| **Versehentliche Zerstörung** | Systemdateien können unbeabsichtigt gelöscht werden |
| **Grössere Angriffsfläche** | Jede Sicherheitslücke hat direkt Root-Zugriff |

---

## Merksatz

> Arbeite immer als **normaler Benutzer** – nutze Admin-Rechte **nur wenn nötig** und nur für einzelne Befehle.

---

## Verknüpfungen

→ [[06 - Benutzer und Gruppen]]
→ [[08 - SSH]]
→ [[Befehle-Cheatsheet]]
