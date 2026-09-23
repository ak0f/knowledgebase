# Datenschutz und Berechtigungen

**Modul:** Datenschutz und Berechtigungen (100)
**Tags:** #SQL #MySQL #Datenschutz #DCL #Rechte

---

## Lernziele

- [ ] Datenbankbenutzer mit MySQL erstellen
- [ ] Erstellten Datenbankbenutzern vorgegebene Rechte auf Datenbanken bzw. Tabellen vergeben

---

## Datenschutz – Rechtliche Grundlagen

**Bundesverfassung Art. 13**

1. Jede Person hat Anspruch auf Achtung ihres Privat- und Familienlebens, ihrer Wohnung sowie ihres Brief-, Post- und Fernmeldeverkehrs.
2. Jede Person hat Anspruch auf Schutz vor Missbrauch ihrer persönlichen Daten.

**Datenschutzgesetz Art. 7**

> Personendaten müssen durch angemessene technische und organisatorische Massnahmen gegen unbefugtes Lesen und Bearbeiten geschützt werden.

**Datenschutzgesetz Art. 3c** – Besonders schützenswerte Personendaten:

1. Religiöse, weltanschauliche, politische oder gewerkschaftliche Ansichten oder Tätigkeiten
2. Gesundheit, Intimsphäre oder Rassenzugehörigkeit
3. Massnahmen der sozialen Hilfe
4. Administrative oder strafrechtliche Verfolgungen und Sanktionen

---

## Aufbau von SQL – Data Control Language (DCL)

Benutzerverwaltung und Rechte:

- `CREATE / DROP USER` – Benutzer hinzufügen / entfernen
- `GRANT / REVOKE` – Rechte hinzufügen / entfernen

> DCL wird verwendet, um Benutzer und deren Rechte zu administrieren.

---

## Benutzer erstellen

```sql
CREATE USER benutzer@hostname
IDENTIFIED BY password;
```

**Beispiel – nur lokaler Zugriff:**

```sql
CREATE USER hr_manager@localhost
IDENTIFIED BY 'secret';
```

User `hr_manager` wird nur für den lokalen Host erstellt = Zugriff nur vom lokalen Host aus möglich.

**Beispiel – Zugriff von überall:**

```sql
CREATE USER hr_manager@'%'
IDENTIFIED BY 'secret';
```

User `hr_manager` wird für alle Hosts erstellt = Zugriff von jedem Host aus möglich. Das `%` ist ein Platzhalter, gleiche Bedeutung wie `*`.

---

## Zugriffsrechte vergeben

| Scope | Bedeutung |
|-------|-----------|
| `*.*` | Rechte gelten für alle DBs und alle Tabellen |
| `Datenbank.*` | Rechte gelten für alle Tabellen einer bestimmten DB |
| `Datenbank.Tabelle` | Rechte gelten für die angegebene Tabelle |

> Standardmässig kann nur `root` Rechte vergeben.

```sql
GRANT rechteliste ON db.tabelle
TO benutzer@hostname;
```

**Beispiel:**

```sql
GRANT ALL ON firma.mitarbeiter
TO hr_manager@localhost;

GRANT SELECT, INSERT, DELETE
ON firma.mitarbeiter
TO hr_manager@localhost;
```

> Mit nur `SELECT, INSERT, DELETE` kann `hr_manager` **keine** bestehenden Datensätze aktualisieren – dafür fehlt das Recht `UPDATE`.

---

## Zugriffsrechte entziehen

Rechte können jederzeit wieder mit `REVOKE` entzogen werden.

```sql
REVOKE rechteliste ON db.tabelle
FROM benutzer@hostname;

REVOKE ALL ON firma.mitarbeiter
FROM hr_manager@localhost;
```

---

## Benutzer löschen

Zwei Möglichkeiten:

```sql
-- 1. Benutzer mit DROP löschen
DROP USER hr_manager@localhost;

-- 2. Datensatz in der Tabelle [MYSQL.]USER löschen
DELETE FROM [MYSQL.]USER
WHERE user = 'hr_manager';
```

Benutzer können auch über das Management-Tool (MySQL Workbench) verwaltet werden.

---

## Verknüpfungen

→ [[01 - SQL-Datentypen]]
→ [[03 - Datenmigration]]
→ [[Befehle-Cheatsheet]]
