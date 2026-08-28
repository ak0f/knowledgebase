# Dateisystemrechte

**Modul:** Dateisystemrechte (210)
**Tags:** #Linux #Rechte #chmod #chown

---

## Lernziele

- [ ] `ls -l` Ausgabe vollständig lesen und verstehen
- [ ] Rechtesystem (rwx) erklären
- [ ] Oktalwerte berechnen
- [ ] chmod anwenden (symbolisch und oktal)
- [ ] chown anwenden

---

## ls -l Ausgabe lesen

```
drwxr-xr-x  3  tux  tux  4096  Sep 17 09:41  .
```

| Teil | Bedeutung |
|------|-----------|
| `d` | Typ (d=Verzeichnis, -=Datei, l=Link) |
| `rwx` | Rechte Eigentümer (Owner) |
| `r-x` | Rechte Gruppe |
| `r-x` | Rechte Andere (Others) |
| `3` | Anzahl Hardlinks |
| `tux` | Eigentümer |
| `tux` | Gruppe |
| `4096` | Grösse in Bytes |
| `Sep 17 09:41` | Datum/Uhrzeit |
| `.` | Name |

---

## Rechte (rwx)

| Symbol | Recht | Wert |
|--------|-------|------|
| `r` | read (lesen) | **4** |
| `w` | write (schreiben) | **2** |
| `x` | execute (ausführen) | **1** |
| `-` | kein Recht | 0 |

---

## Oktalwerte berechnen

```
rwxr-xr-x = 755

r w x  r - x  r - x
4+2+1  4+0+1  4+0+1
  7      5      5
```

**Häufige Werte:**

| Oktal | Symbol | Bedeutung |
|-------|--------|-----------|
| `777` | `rwxrwxrwx` | Alle dürfen alles |
| `755` | `rwxr-xr-x` | Standard Verzeichnis |
| `644` | `rw-r--r--` | Standard Datei |
| `700` | `rwx------` | Nur Eigentümer |
| `000` | `---------` | Niemand |

---

## chmod – Rechte setzen

```bash
# Oktal (direkt)
chmod 755 datei
chmod 644 datei.txt

# Symbolisch
chmod u=rwx,g=rx,o=rx datei   # setzen
chmod o-w datei                 # entfernen
chmod u+x script.sh             # hinzufügen

# Rekursiv (ganzer Ordner)
chmod -R 755 /home/tux/dateien
```

**Kürzel:**
- `u` = user (Eigentümer)
- `g` = group (Gruppe)
- `o` = others (Andere)
- `a` = all (alle)

---

## chown – Eigentümer ändern

```bash
# Nur Eigentümer ändern
chown benutzer datei

# Eigentümer und Gruppe ändern
chown benutzer:gruppe datei
```

---

## Verknüpfungen

→ [[06 - Benutzer und Gruppen]]
→ [[07 - Administrationsrechte]]
→ [[Befehle-Cheatsheet]]
