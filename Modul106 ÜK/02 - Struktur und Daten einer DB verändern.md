# Struktur und Daten einer DB verändern

**Modul:** SQL – Struktur und Daten einer DB verändern (100)
**Tags:** #SQL #DDL #DML #DQL

---

## Lernziele

- [ ] Die Struktur von Tabellen verändern
- [ ] Die Daten in den Tabellen verändern
- [ ] Daten, Tabellen und Datenbanken löschen
- [ ] Daten gefiltert und sortiert auslesen

---

## Aufbau von SQL – Sprachschichten

| Schicht | Zweck | Befehle |
|---------|-------|---------|
| **DDL** – Data Definition Language | Struktur bearbeiten | `CREATE`, `EXPLAIN`, `ALTER`, `DROP` |
| **DML** – Data Manipulation Language | Inhalte bearbeiten | `INSERT`, `UPDATE`, `DELETE` |
| **DQL** – Data Query Language | Inhalte auslesen | `SELECT` |

> DDL sollte in der Regel nur beim Anlegen einer DB verwendet werden. DML und DQL werden immer wieder verwendet, um Daten zu bearbeiten bzw. auszulesen.

---

## DDL – Tabellen verändern

Einzelne Attribute können mit `ALTER` nachträglich zu einer Tabelle hinzugefügt oder gelöscht werden.

```sql
-- Feld hinzufügen (optional FIRST oder AFTER col)
ALTER TABLE tabellen_name
ADD COLUMN spalten_name datentyp [FIRST|AFTER column_name_2];

-- Feld ändern (Name und/oder Datentyp)
ALTER TABLE tabellen_name
CHANGE COLUMN spalten_name spalten_name_neu datentyp_neu;

-- Feld löschen
ALTER TABLE tabellen_name
DROP COLUMN spalten_name;
```

---

## DDL – Tabelle / Datenbank löschen

```sql
DROP TABLE tabellen_name;
DROP DATABASE datenbank_name;
```

> **Achtung:** Löscht ohne zu fragen die Tabelle inkl. Inhalt! Dieser Befehl sollte bei guter Planung eigentlich nie gebraucht werden.

---

## DML – Werte verändern

Einmal geschriebene Entitäten werden mit `UPDATE` verändert. Wie beim `SELECT` wird auch hier mit `WHERE` und oft mit der ID gearbeitet.

```sql
UPDATE tabellen_name
SET spaltename_X = 'neuer Wert'
    [, spaltename_Y = 'neuer Wert', ...]
WHERE spaltename_Z = 'XYZ';
```

---

## DML – Werte löschen

```sql
DELETE FROM tabellen_name;
DELETE FROM tabellen_name WHERE bedingung;
```

> **Achtung:** Ohne `WHERE` werden alle Inhalte gelöscht! Jede Entität bedeutet Zeit und Geld.

**Safe Updates:** unter *Edit > Preferences...* in MySQL Workbench aktivierbar/deaktivierbar (Workbench danach neu starten).

---

## DQL – Gezieltes Auslesen

Einzelne Entitäten können direkt angesprochen werden – ID oder Inhalt eines Attributes in der Bedingung angeben.

```sql
SELECT spaltename_X [, spaltename_Y, ...]
FROM tabellen_name
WHERE bedingung;
```

### Verknüpfungen von Bedingungen

Eine Query kann sich aus mehreren Bedingungen zusammensetzen. `AND` und `OR` sind die beiden Kombinationsmöglichkeiten.

```sql
SELECT spaltename_X, ...
FROM tabellen_name
WHERE bedingung
  AND bedingung2
  OR bedingung3;
```

### Geordnetes Auslesen

Entitäten werden selten in brauchbarer Reihenfolge eingegeben – `ORDER BY` sortiert die Ausgabe.

```sql
SELECT spaltename_X, ...
FROM tabellen_name
ORDER BY spaltename_X ASC|DESC;
```

---

## Verknüpfungen

→ [[01 - SQL-Datentypen]]
→ [[05 - Joins und Aggregationsfunktionen]]
→ [[Befehle-Cheatsheet]]
