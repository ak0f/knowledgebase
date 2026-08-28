# Befehle-Cheatsheet – Modul 187 ÜK

> Schnellreferenz aller wichtigen Befehle und Tastenkombinationen

---

## Netzwerk (Windows CMD)

```bash
ipconfig              # IP, Subnetzmaske, Gateway aller Adapter anzeigen
ipconfig /all         # Zusätzlich MAC-Adresse, DHCP-Server, DNS
ipconfig /release     # IP-Adresse freigeben
ipconfig /renew       # Neue IP per DHCP anfordern
ipconfig /flushdns    # DNS-Cache leeren

ping 8.8.8.8          # Erreichbarkeit von Google DNS testen
ping google.com       # DNS-Auflösung + Erreichbarkeit prüfen
ping 127.0.0.1        # Lokalen TCP/IP-Stack testen (Loopback)

nslookup google.com   # Domainnamen in IP auflösen
nslookup 8.8.8.8      # Reverse-Lookup (IP → Name)
```

---

## Windows-Systemverwaltung

```powershell
# Gerätemanager
devmgmt.msc           # Gerätemanager öffnen

# Dienste & Autostart
msconfig              # Systemkonfiguration (Dienste, Boot)
taskschd.msc          # Aufgabenplanung (geplante Tasks)
shell:startup         # Autostart-Ordner im Explorer öffnen

# Speicher & System
cleanmgr              # Datenträgerbereinigung
diskmgmt.msc          # Datenträgerverwaltung
```

---

## Windows-Sicherheit & Firewall

```powershell
# Windows-Sicherheitscenter öffnen
ms-settings:windowsdefender

# Firewall (erweiterte Einstellungen)
wf.msc                # Windows Firewall mit erweiterter Sicherheit

# Windows Update
ms-settings:windowsupdate

# Ereignisanzeige (Logs)
eventvwr.msc
```

---

## Energieverwaltung

```powershell
powercfg /list                   # Alle Energiepläne anzeigen
powercfg /query                  # Details des aktiven Plans
powercfg /batteryreport          # Akkubericht erstellen (Laptops)
powercfg /energy                 # Energieeffizienz-Bericht
```

---

## Wichtige Windows-Tastenkombinationen

| Shortcut | Funktion |
|---------|---------|
| `Win + E` | Explorer öffnen |
| `Win + R` | Ausführen-Dialog |
| `Win + I` | Einstellungen |
| `Win + Pause` | Systeminformationen |
| `Ctrl + Shift + Esc` | Task-Manager direkt |
| `Alt + F4` | Programm schliessen |
| `Win + Pfeiltaste` | Fenster andocken |
| `Win + L` | Bildschirm sperren |

---

## Nützliche Ausführen-Befehle (Win+R)

| Befehl | Öffnet |
|--------|--------|
| `devmgmt.msc` | Gerätemanager |
| `eventvwr.msc` | Ereignisanzeige |
| `msinfo32` | Systeminformationen |
| `wf.msc` | Firewall (erweitert) |
| `msconfig` | Systemkonfiguration |
| `cleanmgr` | Datenträgerbereinigung |
| `taskschd.msc` | Aufgabenplanung |
| `control` | Systemsteuerung |

---

## Bit & Byte Umrechnung

| Einheit | Wert |
|--------|------|
| 1 Byte | 8 Bit |
| 1 KB | 1024 Byte |
| 1 MB | 1024 KB |
| 1 GB | 1024 MB |
| 1 GB/s | 8 Gbit/s |

---

## IP-Adressen Kurzübersicht

| Bereich | Typ |
|--------|-----|
| `10.0.0.0 – 10.255.255.255` | Privat |
| `172.16.0.0 – 172.31.255.255` | Privat |
| `192.168.0.0 – 192.168.255.255` | Privat |
| `169.254.0.0 – 169.254.255.255` | APIPA (kein DHCP!) |
| `127.0.0.1` | Loopback (localhost) |

---

## Verknüpfungen

→ [[00 - MOC]]
→ [[Pruefungsvorbereitung UEK]]
