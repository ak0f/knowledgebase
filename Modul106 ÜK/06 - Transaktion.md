# Transaktion

**Modul:** Transaktion (100)
**Tags:** #SQL #Transaktion #ACID #TCL

---

## Lernziele

- [ ] Erklären, was eine Transaktion ist und wozu diese gebraucht wird
- [ ] In MySQL mehrere SQL-Statements in eine Transaktion zusammenfassen
- [ ] Eine Transaktion mit `COMMIT` bestätigen oder mit `ROLLBACK` zurücksetzen

---

## Das Problem

Geld von einem Konto auf ein anderes überweisen:

```sql
UPDATE konto SET saldo = saldo - 500 WHERE konto_nr = 786345343;
UPDATE konto SET saldo = saldo + 500 WHERE konto_nr = 123325932;
```

Wenn das zweite `UPDATE` fehlschlägt (z.B. ungültige Kontonummer), wäre das Geld vom ersten Konto abgebucht, aber nirgends gutgeschrieben – **Geld wäre verloren**.

---

## Was ist eine Transaktion?

Eine Transaktion fasst mehrere Arbeitsschritte zusammen und sorgt dafür, dass diese **alle zusammen** ausgeführt werden, oder **alle zusammen nicht** ausgeführt werden (Alles-oder-nichts-Prinzip).

### ACID-Kriterien

| Kriterium | Bedeutung |
|-----------|-----------|
| **A**tomic | Unteilbarkeit – Alles-oder-nichts-Prinzip |
| **C**onsistent | Konsistenz – war das System vor der Transaktion in einem gültigen Zustand, ist es das auch nachher |
| **I**solated | Isolierung – Transaktionen laufen ungestört von anderen ab (keine gleichzeitige Bearbeitung derselben Daten) |
| **D**urable | Dauerhaftigkeit – mit `COMMIT` abgeschlossene Änderungen sind persistent |

---

## Aufbau von SQL – Transaction Control Language (TCL)

- `START TRANSACTION` – Transaktion beginnen
- `COMMIT` / `ROLLBACK` – Transaktion bestätigen / abbrechen

> TCL wird verwendet, um Transaktionen zu kontrollieren.

---

## Die Lösung

```sql
START TRANSACTION;
UPDATE konto SET saldo = saldo - 500 WHERE konto_nr = 786345343;
UPDATE konto SET saldo = saldo + 500 WHERE konto_nr = 123325932;
COMMIT;
-- oder bei Fehler:
ROLLBACK;
```

- `INSERT`-, `UPDATE`-, `DELETE`-Anweisungen werden in einer Transaktion zusammengefasst
- Mit `COMMIT` bestätigen oder mit `ROLLBACK` wieder den Ursprungszustand herstellen
- Die Fallunterscheidung (ob committed oder rollback wird) erfolgt nicht direkt in SQL, sondern in der darüberliegenden Programmschicht

---

## Autocommit-Modus

- **Autocommit** ist per Default aktiviert – Änderungen werden direkt in die Datenbank geschrieben
- Deaktivieren mit `SET AUTOCOMMIT=0;` → alle Änderungen müssen dann mit `COMMIT` bestätigt werden
- Ein `START TRANSACTION` setzt das normalerweise aktivierte Autocommit nur so lange ausser Kraft, bis die Transaktion mit `COMMIT` oder `ROLLBACK` abgeschlossen wurde

---

## Verknüpfungen

→ [[02 - Struktur und Daten einer DB verändern]]
→ [[07 - DB-optimieren]]
→ [[Befehle-Cheatsheet]]
