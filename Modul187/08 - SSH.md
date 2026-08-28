# SSH – Secure Shell

**Modul:** SSH (210)
**Tags:** #SSH #Netzwerk #Fernzugriff #Sicherheit

---

## Lernziele

- [ ] SSH = Secure Shell – Bedeutung erklären
- [ ] **3 Anwendungsfälle** von SSH nennen
- [ ] SSH-Verbindungsablauf beschreiben (Authentifizierung → Shell → Austausch)
- [ ] `ssh benutzername@ip-adresse` anwenden
- [ ] BbcNet → SSH → EduNet erklären

---

## Was ist SSH?

**SSH = Secure Shell**
- Verschlüsseltes Netzwerkprotokoll
- Ermöglicht sicheren Fernzugriff auf Geräte über unsichere Netzwerke

---

## Wozu wird SSH genutzt?

1. **Remote Login** – Entferntes Anmelden auf Servern/Geräten
2. **Geräteverwaltung** – Konfiguration über das Netzwerk
3. **Sichere Datenübertragung** – Dateitransfer (SCP, SFTP)

---

## SSH Verbindungsablauf

```
Client                          Server
  |                                |
  |--- Verbindungsanfrage -------> |
  |<-- Authentifizierung --------- |
  |    (Benutzername + Passwort)   |
  |                                |
  |--- Shell startet (Bash) -----> |
  |<-- Bidirektionaler Austausch ->|
```

---

## SSH Befehl

```bash
ssh benutzername@ip-adresse

# Beispiel
ssh akif@192.168.1.100
```

---

## BBC Kontext – BbcNet & EduNet

```
BbcNet (produktiv)  →  SSH  →  EduNet (Labor)
```

- Von **BbcNet** (produktives Schulnetz) mit SSH auf **EduNet**-Geräte verbinden
- EduNet = separates Labornetz (mehr Experimentierfreiheit)

---

## Sicherheit

- Verbindung ist **verschlüsselt** (kein Klartext)
- Alternative zu unverschlüsseltem `telnet`
- Authentifizierung: Passwort oder SSH-Key

---

## Verknüpfungen

→ [[07 - Administrationsrechte]]
→ [[09 - Labor EduNet]]
→ [[Befehle-Cheatsheet]]
