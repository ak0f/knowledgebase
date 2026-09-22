# SQL-Datentypen

**Modul:** MySQL Datentypen (100)
**Tags:** #SQL #MySQL #Datentypen

---

## Lernziele

- [ ] Die verschiedenen Datentypen in einer Datenbank kennen
- [ ] Die korrekten Datentypen einsetzen (Zahlenformate, Textformate, Date/Time)
- [ ] Ein Passwort verschlüsselt auf der DB ablegen

---

## Ganzzahlen

| Datentyp | Speicherverbrauch | Minimaler Wert | Maximaler Wert |
|----------|-------------------|-----------------|------------------|
| `TINYINT` | 1 byte | -128 | 127 |
| `SMALLINT` | 2 bytes | -32768 | 32767 |
| `MEDIUMINT` | 3 bytes | -8388608 | 8388607 |
| `INT` | 4 bytes | -2147483648 | 2147483647 |
| `BIGINT` | 8 bytes | -2^63 | 2^63-1 |

> `INT(11)` hat **keinen** Einfluss auf die Grösse der gespeicherten Zahl! Die 11 ist die "display width" – wie viele Stellen sollen angezeigt werden.
> `UNSIGNED` für Zahlen ohne Vorzeichen.

---

## Kommazahlen

| Datentyp | Eigenschaft |
|----------|-------------|
| `FLOAT` | Fliesskommazahl, 4 Bytes – exakt bis 7 Stellen (inkl. Punkt) |
| `DOUBLE` | Fliesskommazahl mit doppelter Genauigkeit, 8 Bytes – exakt bis 15 Stellen (inkl. Punkt) |
| `DECIMAL(M, D)` | Fixkommazahl (exakter Wert). M = Anzahl Ziffern gesamt, D = Anzahl Ziffern nach dem Komma |

Beispiel `DECIMAL(5,2)` → Bereich -999.99 bis 999.99

**Wann was?**
- Wissenschaftliche Daten (Mathematik, Physik, Chemie) → `FLOAT` / `DOUBLE`
- Vom Menschen erfundene Zahlensysteme (Finanzen, Punkte, Noten) → `DECIMAL`

---

## Textformate

| Datentyp | Eigenschaft |
|----------|-------------|
| `CHAR(m)` | Zeichenkette fester Länge, max. 255 Zeichen |
| `VARCHAR(m)` | Zeichenkette variabler Länge, max. 65'535 Zeichen |
| `TEXT` | Längerer Text, variable Länge, extern gespeichert, etwas langsamer |
| `LONGTEXT` | Text mit variabler Länge, max. 4.2 GB |

---

## Date / Time

| Datentyp | Format | Bereich |
|----------|--------|---------|
| `DATE` | `YYYY-MM-DD` | '1000-01-01' bis '9999-12-31' |
| `TIME` | `[h]hh:mm:ss` | '-838:59:59' bis '838:59:59' |
| `DATETIME` | `YYYY-MM-DD hh:mm:ss[.fraction]` | '1000-01-01 00:00:00' bis '9999-12-31 23:59:59' |
| `TIMESTAMP` | `YYYY-MM-DD hh:mm:ss[.fraction]` | '1970-01-01 00:00:01' UTC bis '2038-01-19 03:14:07' UTC |

```sql
CREATE TABLE person (
  id           INT PRIMARY KEY AUTO_INCREMENT,
  name         VARCHAR(250),
  geburtsdatum DATE
);

INSERT INTO person (name, geburtsdatum)
VALUES ("Mona", "1993-05-15"), ("Lisa", "1998-07-23");

SELECT * FROM person
WHERE geburtsdatum < current_date;

SELECT * FROM person
WHERE year(geburtsdatum) < 1995
ORDER BY geburtsdatum DESC;
```

### DEFAULT / ON UPDATE

```sql
CREATE TABLE friend (
  id         INT PRIMARY KEY AUTO_INCREMENT,
  name       VARCHAR(50) NOT NULL,
  birthday   DATE NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
```

---

## Weitere Datentypen

- **`BOOL`** – gleich wie `TINYINT(1)`, 0 ist false, der Rest true
- **`ENUM`** – Liste von möglichen Werten
- **`BLOB`** – Dateien (z.B. Bilder)

```sql
CREATE TABLE pic (
  id  INT AUTO_INCREMENT PRIMARY KEY,
  img LONGBLOB NOT NULL
);

INSERT INTO pic (img)
VALUES (LOAD_FILE('myImage.png'));
```

---

## Passwort Hashing

Passwörter nie im Klartext speichern – immer gehasht mit `SHA2()`.

```sql
CREATE TABLE person (
  id           INT AUTO_INCREMENT PRIMARY KEY,
  benutzername VARCHAR(250),
  passwort     VARCHAR(128),
  geburtsdatum DATE
);

INSERT INTO person (benutzername, passwort, geburtsdatum)
VALUES ("Mona", SHA2("passwd", 512), "1995-05-15");
```

---

## Verknüpfungen

→ [[02 - Struktur und Daten einer DB verändern]]
→ [[04 - Datenschutz und Berechtigungen]]
→ [[Befehle-Cheatsheet]]
