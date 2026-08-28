# Linux Kennenlernen

**Modul:** Linux Kennenlernen (210)
**Tags:** #Linux #Shell #Bash #Befehle

---

## Lernziele

- [ ] Shell erklären und Typen nennen (bash, sh, zsh...)
- [ ] Prompt-Aufbau erklären: `user@hostname:verzeichnis$`
- [ ] Befehlsstruktur erklären: `kommando [optionen] [argumente]`
- [ ] `ls`, `cd`, `pwd`, `mv`, `cp`, `cat`, `grep` anwenden
- [ ] Wildcards anwenden: `*`, `?`, `[1-4]`
- [ ] Umleitung `>`, `>>` und Pipe `|` erklären und anwenden

---

## Shell

**Shell** = Schnittstelle zum Betriebssystem (Kommandozeile)

**Shell-Typen:**
- `sh` – Bourne Shell (älteste)
- **`bash`** – Standard (Bourne Again Shell)
- `zsh` – erweitert
- `Fish`, `ksh`, `sash`

**Aktuelle Shell anzeigen:**
```bash
echo $SHELL
```

**Prompt:**
```
user@hostname:verzeichnis$
```
- `~` = Heimverzeichnis des Benutzers

---

## Befehlsstruktur

```
Kommando  Option(en)  Argument(e)
   ls        -l        file1.txt
```

**Hilfe:**
```bash
man ls          # Handbuch
ls --help       # Kurzinfo
apropos suche   # Stichwortsuche im Handbuch
```

---

## Wichtige Befehle

| Befehl | Bedeutung |
|--------|-----------|
| `ls` | Verzeichnis auflisten |
| `ls -l` | Ausführliche Liste |
| `ls -a` | Versteckte Dateien anzeigen |
| `cd /pfad` | Verzeichnis wechseln |
| `pwd` | Aktuelles Verzeichnis anzeigen |
| `mv QUELLE ZIEL` | Verschieben / Umbenennen |
| `cp QUELLE ZIEL` | Kopieren |
| `cp -r QUELLE ZIEL` | Ordner kopieren |
| `cat DATEI` | Dateiinhalt anzeigen |
| `grep SUCHBEGRIFF DATEI` | In Datei suchen |
| `grep -i` | Gross-/Kleinschreibung ignorieren |
| `grep -r` | Rekursiv suchen |

---

## Wildcards (Platzhalter)

| Wildcard | Bedeutung | Beispiel |
|----------|-----------|---------|
| `*` | Null oder mehr Zeichen | `ls *.txt` |
| `?` | Genau ein Zeichen | `ls file?.txt` |
| `[1-4]` | Bereich | `ls file[1-4].txt` |

---

## Dateinamen in Linux

- **Keine** Umlaute (ä, ö, ü)
- **Keine** Leerzeichen
- **Keine** Sonderzeichen

---

## Tastaturkürzel

| Kürzel | Funktion |
|--------|----------|
| `Ctrl+A` | Zeilenanfang |
| `Ctrl+E` | Zeilenende |
| `Ctrl+C` | Abbruch |
| `↑ / ↓` | Befehlsverlauf |
| `Ctrl+R` | Verlauf durchsuchen |
| `TAB` | Autovervollständigung |

---

## Umleitung und Pipe

```bash
# Ausgabe in Datei schreiben (überschreiben)
ls > dateiliste.txt

# Ausgabe anhängen
ls >> dateiliste.txt

# Pipe: Ausgabe weiterleiten
cat datei.txt | grep "Inhalt"
```

---

## Verknüpfungen

→ [[04 - Datei- und Verzeichnisstruktur]]
→ [[05 - Dateisystemrechte]]
→ [[Befehle-Cheatsheet]]
