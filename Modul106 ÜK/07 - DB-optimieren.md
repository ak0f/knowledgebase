# Datenbank optimieren

**Modul:** Datenbank optimieren (100)
**Tags:** #SQL #Performance #Index #Optimierung

---

## Lernziele

- [ ] Wissen, welche Faktoren die Performance von Datenbankabfragen beeinflussen
- [ ] Wissen, wie die auf dem Server gespeicherten Daten optimiert werden können
- [ ] Die Performance von SQL-Queries mit Hilfe von Indizes verbessern

---

## Performancerelevante Faktoren

- Hardware (Disk, CPU)
- Netzwerk
- Query-Komplexität (`JOIN`, `WHERE`, `ORDER BY`)
- Datenmenge
- Resultatgrösse
- Fragmentierung
- Weitere Prozesse auf dem Server

---

## Performance messen

- **MySQL Workbench "Output"-View:**
  - *Duration* – Dauer des Queries auf dem Server
  - *Fetch* – Dauer für das Holen und Übertragen der Daten
- **`EXPLAIN`**-Statement vor das Query setzen → zeigt eine Analyse des Queries an

```sql
EXPLAIN SELECT * FROM mitarbeiter WHERE firma_id = 3;
```

---

## Datenbankinformationen auslesen

Die **`information_schema`**-Datenbank ist auf jedem MySQL-Server vorhanden und stellt viele Informationen zur Verfügung (vorhandene Datenbanken/Tabellen, Speichernutzung, etc.).

```sql
use information_schema;
show tables;             -- Namen der Tabellen anzeigen
select * from schemata;  -- Alle Datenbanken des Servers anzeigen
select * from tables;    -- Alle Tabellen anzeigen

-- Grösse der Tabellen einer Datenbank auslesen (Beispiel: DB "ip")
SELECT
    table_schema AS datenbank,
    table_name AS tabelle,
    ROUND(((data_length + index_length) / 1024 / 1024), 2) AS size_in_mb
FROM information_schema.tables
WHERE table_schema = 'ip';
```

---

## Performance Impact: Fragmentierung

Mit dem Ändern und Löschen von Datensätzen können die entsprechenden Daten wie bei einem Dateisystem fragmentiert werden.

```sql
SHOW TABLE STATUS;      -- zeigt u.a. die Fragmentierung
OPTIMIZE TABLE tablename; -- optimiert die Speichernutzung
```

| Feld | Bedeutung |
|------|-----------|
| `Data_length` | Grösse der eigentlichen Daten |
| `Index_length` | Grösse der Indizes |
| `Data_free` | Freier Speicher zwischen den Daten |

> Die Fragmentierung macht für die Performance meist nur wenig aus.

---

## Performance Impact: Resultatgrösse

Je mehr Daten auf dem Server gelesen und an den Client gesendet werden müssen, desto langsamer die Abfrage.

**Mögliche Optimierungen:**

- `SELECT * FROM ...` vermeiden – nur die nötigen Attribute laden
- Anzahl Datensätze limitieren

```sql
SELECT * FROM table LIMIT 100;      -- erste 100 Datensätze
SELECT * FROM table LIMIT 100, 100; -- nächste 100
```

---

## Performance Impact: Komplexe Queries – Indizes

`JOIN`-, Filter- und Sortieroperationen sind fast immer notwendig, erfordern aber viel Rechenleistung. Diese Operationen können mit **Indizes** optimiert werden.

- Ein Index ist eine Suchhilfe für ein bestimmtes Attribut
- Lohnt sich für Attribute, die in `JOIN`, `WHERE` oder `ORDER BY` gebraucht werden
- Primärschlüssel werden standardmässig indexiert

```sql
ALTER TABLE location ADD INDEX idx_location_city (city);
```

---

## Verknüpfungen

→ [[02 - Struktur und Daten einer DB verändern]]
→ [[05 - Joins und Aggregationsfunktionen]]
→ [[06 - Transaktion]]
→ [[Befehle-Cheatsheet]]
