# Datenmigration

**Modul:** Datenmigration – Daten importieren und exportieren (100)
**Tags:** #SQL #MySQL #Datenmigration #CSV

---

## Lernziele

- [ ] In MySQL Workbench Datenbanken in ein Dump File exportieren und später wieder herstellen (importieren)
- [ ] Den SQL-Befehl kennen, um Daten aus einer .csv-Datei in eine Datenbank zu importieren
- [ ] Wissen, worauf beim Import aus einer .csv-Datei zu achten ist

---

## Export / Import über Dump File

MySQL Workbench kann eine ganze Datenbank als **Dump File** exportieren und dieses File später wieder in eine (leere) Datenbank importieren. Damit lässt sich der komplette Stand einer DB sichern oder auf ein anderes System übertragen.

---

## Datenmigration (Quelle → Ziel)

Was tun, wenn Daten migriert werden sollen?

1. Die Quellstruktur gut kennen
2. In die Struktur des Zielsystems einarbeiten
3. Allenfalls Anpassungen an den Quelldaten durchführen
4. Daten ins Zielsystem importieren
5. Daten im Zielsystem testen (Anzahl, Werte, Fremdschlüssel, ...)
6. Allenfalls Daten bereinigen

### Testen

- [ ] Anzahl Datensätze komplett
- [ ] Quellfelder in den richtigen Zielfeldern
- [ ] Werte korrekt formatiert
- [ ] Korrekte Relationen zwischen Tabellen (Fremdschlüssel)
- [ ] Datenkonsistenz prüfen

---

## Import von Daten aus CSV-Datei

```sql
LOAD DATA INFILE 'C:\\ProgramData\\MySQL\\MySQL Server 8.0\\Uploads\\test.csv'
INTO TABLE test
CHARACTER SET utf8mb4
FIELDS TERMINATED BY ';'
LINES TERMINATED BY '\r\n'
IGNORE 1 ROWS
(id, name, vorname);
```

**Wichtige Punkte:**

- `LOAD DATA INFILE` liest nur Files aus dem erlaubten Ordner:
  ```sql
  show variables like 'secure_file_priv';
  ```
  Vermutlich: `C:\ProgramData\MySQL\MySQL Server 8.0\Uploads`
- Trennzeichen angeben: `FIELDS TERMINATED BY ';'`
- Zeilenende angeben: `LINES TERMINATED BY '\r\n'` (Windows – Linux nur `\n`)
- Zeilen ignorieren (z.B. Header): `IGNORE num {LINES|ROWS}`
- Spaltenliste angeben: `(id, name, vorname)` – Spaltennamen wie in der DB-Tabelle, Reihenfolge wie in der CSV-Datei

---

## Achtung mit Fremdschlüsseln

```sql
SET foreign_key_checks = 0; -- Ausschalten
SET foreign_key_checks = 1; -- Wieder einschalten
```

Fremdschlüssel für das Laden der Daten ignorieren:

- Reihenfolge der zu importierenden Tabellen ist beliebig
- Fremdschlüssel werden nicht überprüft
- Kann zu Dateninkonsistenz führen
- Default: `foreign_key_checks = 1`

---

## Verknüpfungen

→ [[02 - Struktur und Daten einer DB verändern]]
→ [[04 - Datenschutz und Berechtigungen]]
→ [[Befehle-Cheatsheet]]
