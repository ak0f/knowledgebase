# Befehle Cheatsheet

> Alle wichtigen SQL-Befehle (MySQL) auf einen Blick.

---

## Datentypen

```sql
-- Ganzzahlen: TINYINT, SMALLINT, MEDIUMINT, INT, BIGINT
-- Kommazahlen: FLOAT, DOUBLE, DECIMAL(M,D)
-- Text: CHAR(m), VARCHAR(m), TEXT, LONGTEXT
-- Date/Time: DATE, TIME, DATETIME, TIMESTAMP
-- Weitere: BOOL, ENUM, BLOB/LONGBLOB
```

---

## DDL – Struktur (Data Definition Language)

```sql
CREATE TABLE tabellen_name (...);

ALTER TABLE tabellen_name
ADD COLUMN spalten_name datentyp [FIRST|AFTER column_name_2];

ALTER TABLE tabellen_name
CHANGE COLUMN spalten_name spalten_name_neu datentyp_neu;

ALTER TABLE tabellen_name
DROP COLUMN spalten_name;

DROP TABLE tabellen_name;
DROP DATABASE datenbank_name;
```

---

## DML – Inhalte (Data Manipulation Language)

```sql
INSERT INTO tabellen_name (spalte1, spalte2)
VALUES (wert1, wert2);

UPDATE tabellen_name
SET spaltename_X = 'neuer Wert'
WHERE spaltename_Z = 'XYZ';

DELETE FROM tabellen_name WHERE bedingung;
```

---

## DQL – Auslesen (Data Query Language)

```sql
SELECT spaltename_X [, spaltename_Y, ...]
FROM tabellen_name
WHERE bedingung
ORDER BY spaltename_X ASC|DESC;

-- NULL-Filter
WHERE spalte IS NULL;
WHERE spalte IS NOT NULL;

-- IN / NOT IN
WHERE spalte IN ('a', 'b');
WHERE spalte NOT IN (SELECT ...);

-- LIKE
WHERE spalte LIKE '%text%';

-- BETWEEN (inklusiv)
WHERE spalte BETWEEN 'A' AND 'M';
```

---

## Joins

```sql
-- Inner Join (nur Treffer auf beiden Seiten)
SELECT a.spalte, b.spalte
FROM tabelle_a AS a
JOIN tabelle_b AS b ON a.fremdschluessel = b.id;

-- Left Join (alle aus tabelle_a, auch ohne Treffer)
SELECT a.spalte, b.spalte
FROM tabelle_a AS a
LEFT JOIN tabelle_b AS b ON a.fremdschluessel = b.id;

-- Right Join (alle aus tabelle_b, auch ohne Treffer)
SELECT a.spalte, b.spalte
FROM tabelle_a AS a
RIGHT JOIN tabelle_b AS b ON a.fremdschluessel = b.id;
```

---

## Aggregatfunktionen

```sql
SELECT COUNT(*) FROM tabelle;
SELECT AVG(spalte) FROM tabelle;
SELECT SUM(spalte) FROM tabelle;
SELECT MIN(spalte), MAX(spalte) FROM tabelle;

-- GROUP BY / HAVING
SELECT gruppierspalte, COUNT(*) AS anzahl
FROM tabelle
GROUP BY gruppierspalte
HAVING COUNT(*) > 2;
```

---

## DCL – Benutzer & Rechte (Data Control Language)

```sql
CREATE USER benutzer@hostname IDENTIFIED BY 'passwort';
CREATE USER benutzer@'%' IDENTIFIED BY 'passwort';   -- Zugriff von überall

GRANT ALL ON db.tabelle TO benutzer@hostname;
GRANT SELECT, INSERT, DELETE ON db.tabelle TO benutzer@hostname;

REVOKE ALL ON db.tabelle FROM benutzer@hostname;

DROP USER benutzer@hostname;
DELETE FROM mysql.user WHERE user = 'benutzername';
```

**Rechte-Scope:** `*.*` (alle DBs/Tabellen) · `db.*` (alle Tabellen einer DB) · `db.tabelle` (eine Tabelle)

---

## Datenmigration

```sql
-- CSV importieren
LOAD DATA INFILE 'pfad/zur/datei.csv'
INTO TABLE tabellen_name
CHARACTER SET utf8mb4
FIELDS TERMINATED BY ';'
LINES TERMINATED BY '\r\n'
IGNORE 1 ROWS
(spalte1, spalte2, spalte3);

-- Erlaubter Ordner für LOAD DATA INFILE
show variables like 'secure_file_priv';

-- Fremdschlüsselprüfung
SET foreign_key_checks = 0; -- ausschalten (für Import)
SET foreign_key_checks = 1; -- wieder einschalten
```

---

## Passwort Hashing

```sql
INSERT INTO person (benutzername, passwort)
VALUES ("Mona", SHA2("passwd", 512));
```

---

## Verknüpfungen

→ [[00 - MOC]]
→ [[Prüfungsvorbereitung]]
