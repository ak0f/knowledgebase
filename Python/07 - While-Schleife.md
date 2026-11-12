# While-Schleife

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #while #Schleife

> Thema war nicht als PDF vorhanden, selbst zusammengefasst.

---

## Idee

Die `while`-Schleife wiederholt, **solange die Bedingung wahr ist**. Gut, wenn die Anzahl unbekannt ist (z. B. bis eine gültige Eingabe kommt).

```python
count = 1                 # 1. Startwert
while count <= 3:         # 2. Bedingung
    print(count)
    count += 1            # 3. Änderung, sonst Endlosschleife!
```

Ist die Bedingung am Anfang falsch, läuft der Block **nie**.

---

## Endlosschleife

Die Bedingung wird nie falsch (z. B. Variable wird nicht verändert). Abbrechen mit dem Stop-Button oder `Strg + C`.

Absichtlich mit `while True` und `break`:

```python
while True:
    text = input("Eingabe (oder 'stop'): ")
    if text == "stop":
        break
    print(text)
```

---

## Beispiele

**Eingabe prüfen**

```python
age = int(input("Alter: "))
while age < 0 or age > 120:
    print("Ungültig!")
    age = int(input("Alter: "))
```

**Zahlenraten**

```python
import random
secret = random.randint(1, 100)
guess = 0
while guess != secret:
    guess = int(input("Rate: "))
    if guess < secret:
        print("Zu tief")
    elif guess > secret:
        print("Zu hoch")
print("Richtig!")
```

`else` bei einer Schleife läuft nur, wenn **kein** `break` passiert ist.

---

## Typische Fehler

- Änderung der Variable vergessen → Endlosschleife
- `<` statt `<=` → eine Runde zu wenig (Grenzwert)
- `continue` vor der Änderung des Zählers → Endlosschleife
- Startwert fehlt → `NameError`

Jede `for`-Schleife geht auch mit `while`, aber `for` ist bei bekannter Anzahl kürzer und sicherer.

---

→ [[06 - For-Schleife]] · [[08 - Break und Continue]] · [[04 - Boolsche Operatoren]] · [[18 - Debugging]]
