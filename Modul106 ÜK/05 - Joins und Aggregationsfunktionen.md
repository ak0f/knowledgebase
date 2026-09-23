# Joins und Aggregationsfunktionen

**Modul:** Joins und Aggregationsfunktionen (107)
**Tags:** #SQL #Joins #Aggregation #GROUP-BY

---

## Lernziele

- [ ] `NULL`-Werte gezielt filtern (`IS NULL` / `IS NOT NULL`)
- [ ] Mit `IN` / `NOT IN` und Subqueries arbeiten
- [ ] Tabellen mit `JOIN`, `LEFT JOIN` und `RIGHT JOIN` verknüpfen
- [ ] Mit `LIKE` und `BETWEEN` filtern
- [ ] Aggregatfunktionen mit `GROUP BY` und `HAVING` einsetzen

---

## NULL-Werte filtern

```sql
-- alle Mitarbeiter ohne Firma
SELECT name FROM mitarbeiter
WHERE firma_id IS NULL;

-- alle Mitarbeiter mit Firma
SELECT name FROM mitarbeiter
WHERE firma_id IS NOT NULL;
```

---

## IN / NOT IN

```sql
-- Mitarbeiter mit bestimmten Vornamen
SELECT vorname, name
FROM mitarbeiter
WHERE vorname IN ('Kurt', 'Melanie');

-- Firmen ohne Mitarbeiter (Subquery)
SELECT name FROM firma
WHERE id NOT IN (
    SELECT firma_id FROM mitarbeiter
    WHERE firma_id IS NOT NULL
);
```

---

## JOIN – Tabellen verknüpfen

```sql
-- Ohne Aliase
SELECT mitarbeiter.name, firma.name
FROM mitarbeiter
JOIN firma ON firma_id = firma.id;

-- Mit Aliasen (lesbarer)
SELECT m.name AS name, f.name AS firma
FROM mitarbeiter AS m
JOIN firma AS f ON firma_id = f.id;
```

### LEFT JOIN

Gibt **alle** Mitarbeiter zurück, auch wenn sie keiner Firma zugeordnet sind (Firma dann `NULL`).

```sql
SELECT mitarbeiter.name AS name, firma.name AS firma
FROM mitarbeiter
LEFT JOIN firma ON firma_id = firma.id;
```

### RIGHT JOIN

Gibt **alle** Firmen zurück, auch wenn ihnen kein Mitarbeiter zugeordnet ist.

```sql
SELECT mitarbeiter.name AS name, firma.name AS firma
FROM mitarbeiter
RIGHT JOIN firma ON firma_id = firma.id;
```

---

## LIKE – Textsuche

```sql
SELECT firma.name AS firma
FROM firma
WHERE name LIKE '%a%';
```

`%` = beliebig viele Zeichen (auch keins) · `_` = genau ein Zeichen

---

## BETWEEN – Bereich filtern

```sql
SELECT vorname, name
FROM mitarbeiter
WHERE vorname BETWEEN 'K' AND 'P';
```

> `BETWEEN` ist **inklusiv** – beide Grenzwerte gehören zum Ergebnis.

```sql
SELECT COUNT(*) AS anzahl
FROM mitarbeiter
WHERE name BETWEEN 'S' AND 'T';
```

---

## Aggregatfunktionen: GROUP BY / HAVING

`GROUP BY` fasst Zeilen zu Gruppen zusammen, `HAVING` filtert danach auf das Aggregat (im Gegensatz zu `WHERE`, das vor der Gruppierung filtert).

```sql
SELECT firma.name AS firma, COUNT(*) AS 'Anzahl Mitarbeiter'
FROM mitarbeiter
JOIN firma ON firma_id = firma.id
GROUP BY firma.name
HAVING COUNT(*) > 2;
```

### Subquery mit Aggregatfunktion

Durchschnittliche Mitarbeiteranzahl pro Firma berechnen – zuerst pro Firma zählen (Subquery), dann über das Ergebnis mitteln:

```sql
SELECT AVG(anzahl) FROM (
    SELECT firma.name, COUNT(*) AS anzahl
    FROM firma
    JOIN mitarbeiter ON firma.id = firma_id
    GROUP BY firma.name
) AS sub;
```

---

## Verknüpfungen

→ [[02 - Struktur und Daten einer DB verändern]]
→ [[Befehle-Cheatsheet]]
