# Prüfungsvorbereitung – Alle Lernziele

> Hake jedes Lernziel ab wenn du es beherrschst.

---

## Modul 1 – SQL-Datentypen

- [ ] Ganzzahltypen unterscheiden: `TINYINT`, `SMALLINT`, `MEDIUMINT`, `INT`, `BIGINT`
- [ ] `INT(11)` – Display-Width vs. gespeicherte Grösse erklären
- [ ] `FLOAT`/`DOUBLE` (ungenau) vs. `DECIMAL(M,D)` (exakt) unterscheiden und anwenden
- [ ] Textformate wählen: `CHAR(m)`, `VARCHAR(m)`, `TEXT`, `LONGTEXT`
- [ ] Date/Time-Typen und ihre Formate kennen: `DATE`, `TIME`, `DATETIME`, `TIMESTAMP`
- [ ] `DEFAULT CURRENT_TIMESTAMP` / `ON UPDATE CURRENT_TIMESTAMP` anwenden
- [ ] `BOOL`, `ENUM`, `BLOB`/`LONGBLOB` erklären
- [ ] Passwort mit `SHA2()` gehasht ablegen

---

## Modul 2 – Struktur und Daten einer DB verändern

- [ ] DDL / DML / DQL unterscheiden und je 3 Befehle nennen
- [ ] `ALTER TABLE ... ADD COLUMN` anwenden
- [ ] `ALTER TABLE ... CHANGE COLUMN` anwenden
- [ ] `ALTER TABLE ... DROP COLUMN` anwenden
- [ ] `DROP TABLE` und `DROP DATABASE` – Risiken kennen
- [ ] `UPDATE ... SET ... WHERE` korrekt anwenden
- [ ] `DELETE FROM ... WHERE` – Risiko ohne `WHERE` erklären
- [ ] `SELECT ... WHERE ... AND/OR ... ORDER BY` kombinieren

---

## Modul 3 – Datenmigration

- [ ] Export/Import über Dump File in MySQL Workbench beschreiben
- [ ] Migrationsschritte nennen (Quellstruktur kennen → Zielstruktur → Anpassen → Importieren → Testen → Bereinigen)
- [ ] Was beim Testen geprüft wird (Anzahl, Felder, Formatierung, Fremdschlüssel)
- [ ] `LOAD DATA INFILE` korrekt anwenden (Trennzeichen, Zeilenende, IGNORE, Spaltenliste)
- [ ] `secure_file_priv` erklären
- [ ] `SET foreign_key_checks = 0/1` und dessen Risiko erklären

---

## Modul 4 – Datenschutz und Berechtigungen

- [ ] Bundesverfassung Art. 13 – Kerninhalt nennen
- [ ] Datenschutzgesetz Art. 7 – Kerninhalt nennen
- [ ] Datenschutzgesetz Art. 3c – besonders schützenswerte Personendaten (4 Kategorien) nennen
- [ ] DCL erklären (`CREATE/DROP USER`, `GRANT/REVOKE`)
- [ ] `CREATE USER benutzer@localhost` vs. `benutzer@'%'` unterscheiden
- [ ] Rechte-Scope unterscheiden: `*.*`, `db.*`, `db.tabelle`
- [ ] `GRANT` und `REVOKE` korrekt anwenden
- [ ] Benutzer löschen: `DROP USER` vs. `DELETE FROM mysql.user`

---

## Modul 5 – Joins und Aggregationsfunktionen

- [ ] `IS NULL` / `IS NOT NULL` anwenden
- [ ] `IN` / `NOT IN` mit Subquery anwenden
- [ ] `JOIN` mit und ohne Alias schreiben
- [ ] `LEFT JOIN` vs. `RIGHT JOIN` unterscheiden (welche Seite ist vollständig?)
- [ ] `LIKE` mit `%` anwenden
- [ ] `BETWEEN` anwenden und Inklusivität erklären
- [ ] `GROUP BY` mit `COUNT`/`AVG`/`SUM` kombinieren
- [ ] `HAVING` vs. `WHERE` unterscheiden
- [ ] Aggregatfunktion über eine Subquery berechnen (z.B. `AVG` über gruppierte Zwischenresultate)

---

## Modul 6 – Transaktion

- [ ] Erklären, was eine Transaktion ist und wozu sie gebraucht wird
- [ ] Das Alles-oder-nichts-Prinzip an einem Beispiel erklären (Überweisung)
- [ ] ACID-Kriterien nennen und je in einem Satz erklären
- [ ] `START TRANSACTION`, `COMMIT`, `ROLLBACK` korrekt anwenden
- [ ] Autocommit-Modus erklären und mit `SET AUTOCOMMIT=0/1` steuern

---

## Modul 7 – Datenbank optimieren

- [ ] Performancerelevante Faktoren nennen (Hardware, Netzwerk, Query-Komplexität, Datenmenge, Resultatgrösse, Fragmentierung)
- [ ] Performance messen: Duration/Fetch in Workbench, `EXPLAIN` einsetzen
- [ ] `information_schema` nutzen, um Datenbank-/Tabelleninfos auszulesen
- [ ] Fragmentierung erkennen (`SHOW TABLE STATUS`) und beheben (`OPTIMIZE TABLE`)
- [ ] Resultatgrösse optimieren (`SELECT` nur nötige Spalten, `LIMIT`)
- [ ] Index setzen (`ALTER TABLE ... ADD INDEX`) und begründen, wofür sich das lohnt

---

## Schnell-Wiederholung: Wichtigste Befehle

```sql
-- Struktur
ALTER TABLE t ADD COLUMN c datentyp;
DROP TABLE t;

-- Daten
UPDATE t SET c = 'x' WHERE id = 1;
DELETE FROM t WHERE id = 1;

-- Auslesen
SELECT * FROM t WHERE c IS NOT NULL ORDER BY c;

-- Joins
SELECT a.x, b.y FROM a JOIN b ON a.b_id = b.id;
SELECT a.x, b.y FROM a LEFT JOIN b ON a.b_id = b.id;

-- Aggregation
SELECT c, COUNT(*) FROM t GROUP BY c HAVING COUNT(*) > 2;

-- Rechte
CREATE USER u@localhost IDENTIFIED BY 'pw';
GRANT SELECT, INSERT ON db.t TO u@localhost;

-- Migration
LOAD DATA INFILE 'datei.csv' INTO TABLE t
FIELDS TERMINATED BY ';' LINES TERMINATED BY '\r\n' IGNORE 1 ROWS;

-- Transaktion
START TRANSACTION;
UPDATE t SET c = 'x' WHERE id = 1;
COMMIT; -- oder ROLLBACK;

-- Optimierung
EXPLAIN SELECT * FROM t WHERE c = 'x';
ALTER TABLE t ADD INDEX idx_c (c);
```

---

## Verknüpfungen

→ [[00 - MOC]]
→ [[Befehle-Cheatsheet]]
