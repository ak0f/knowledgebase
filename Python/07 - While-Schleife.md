# While-Schleife

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #while #Schleife #Endlosschleife

> Dieses Thema hattest du nicht als PDF. Die Notiz ist selbst verfasst, im gleichen Stil wie die anderen.

---

## Lernziele

- [ ] Eine `while`-Schleife schreiben
- [ ] Schleifenbedingung und Zähler korrekt verwalten
- [ ] Endlosschleifen erkennen und vermeiden
- [ ] Eingaben mit `while` validieren

---

## Idee

Die `while`-Schleife wiederholt einen Block, **solange eine Bedingung wahr ist**. Man nutzt sie, wenn die **Anzahl Wiederholungen nicht bekannt** ist (z. B. bis der Benutzer etwas Gültiges eingibt).

```python
count = 1
while count <= 3:
    print("Durchlauf", count)
    count += 1
```

```
Durchlauf 1
Durchlauf 2
Durchlauf 3
```

**Ablauf:**

1. Bedingung prüfen
2. Wahr → Block ausführen, zurück zu 1
3. Falsch → Schleife verlassen, Code danach läuft weiter

> Ist die Bedingung schon am Anfang falsch, läuft der Block **kein einziges Mal**.

---

## Die drei Teile

```python
number = 10              # 1. Startwert
while number > 0:        # 2. Bedingung
    print(number)
    number -= 3          # 3. Änderung (sonst Endlosschleife!)
```

| Teil | Aufgabe |
|------|---------|
| Startwert | Variable vor der Schleife initialisieren |
| Bedingung | wann weitergemacht wird |
| Änderung | Variable im Block so ändern, dass die Bedingung irgendwann `False` wird |

---

## Endlosschleife

Läuft ewig, weil die Bedingung nie falsch wird.

```python
x = 1
while x > 0:
    print(x)      # x ändert sich nie
```

- In PyCharm abbrechen: roter Stop-Button, im Terminal `Strg + C`
- **Absichtliche** Endlosschleife mit `while True` und `break`:

```python
while True:
    text = input("Eingabe (oder 'stop'): ")
    if text == "stop":
        break
    print("Du hast", text, "eingegeben")
```

---

## Typische Anwendungen

### Eingabe validieren

```python
age = int(input("Alter (0-120): "))
while age < 0 or age > 120:
    print("Ungültig!")
    age = int(input("Alter (0-120): "))
print("Danke!")
```

### Passwort-Abfrage mit Versuchen

```python
password = "geheim"
attempts = 0

while attempts < 3:
    guess = input("Passwort: ")
    if guess == password:
        print("Willkommen!")
        break
    attempts += 1
    print(f"Falsch. Noch {3 - attempts} Versuche.")
else:
    print("Gesperrt.")
```

`else` bei einer Schleife läuft nur, wenn **kein** `break` stattfand.

### Zahlen aufsummieren bis 0

```python
total = 0
number = int(input("Zahl (0 = Ende): "))
while number != 0:
    total += number
    number = int(input("Zahl (0 = Ende): "))
print("Summe:", total)
```

### Countdown

```python
n = 5
while n > 0:
    print(n)
    n -= 1
print("Start!")
```

---

## break und continue

```python
while True:
    value = input("Zahl oder 'x': ")
    if value == "x":
        break                 # Schleife verlassen
    if not value.isdigit():
        continue              # nächster Durchlauf
    print(int(value) * 2)
```

Mehr dazu: [[08 - Break und Continue]]

---

## while vs. for

| | `while` | `for` |
|---|---------|-------|
| Wiederholungen | unbekannt, abhängig von Bedingung | bekannt / jedes Element |
| Zähler | selbst verwalten | automatisch |
| Risiko | Endlosschleife | gering |

Jede `for`-Schleife lässt sich als `while` schreiben, aber `for` ist bei bekannter Anzahl kürzer und sicherer.

```python
# gleich wie: for i in range(1, 4)
i = 1
while i < 4:
    print(i)
    i += 1
```

---

## Typische Fehler

| Fehler | Folge |
|--------|-------|
| Änderung der Variable vergessen | Endlosschleife |
| Falscher Vergleich (`<` statt `<=`) | eine Runde zu wenig/viel (Grenzwert!) |
| Startwert fehlt | `NameError` |
| `=` statt `==` in der Bedingung | `SyntaxError` |
| `continue` vor der Änderung des Zählers | Endlosschleife |

Tipp beim Debuggen: Variable mit `print("count:", count)` beobachten oder Debugger nutzen ([[18 - Debugging]]).

---

## Übungen

1. Zahlen von 1 bis 10 mit `while` ausgeben
2. Zahlenraten: Zufallszahl 1 bis 100, Benutzer rät, Hinweise "zu hoch/zu tief"
3. Programm, das so lange Zahlen addiert, bis die Summe über 100 liegt
4. Menü, das erst bei Eingabe von "q" endet

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

---

## Verknüpfungen

→ [[05 - Entscheidungen mit if, elif und else]]
→ [[06 - For-Schleife]]
→ [[08 - Break und Continue]]
→ [[04 - Boolsche Operatoren]]
