# Standard In / Standard Out

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #stdin #stdout #print #input #EVA

---

## Lernziele

- [ ] EVA-Prinzip und Kommandozeile erklären
- [ ] Mit `print()` ausgeben (inkl. `sep` und `end`)
- [ ] Mit `input()` Eingaben lesen
- [ ] Eingaben in Zahlen umwandeln

---

## Kommandozeile und EVA

- Die Kommandozeile war die **erste Schnittstelle** zwischen Mensch und Computer (vor GUIs und Maus)
- **EVA-Prinzip:** **E**ingabe → **V**erarbeitung → **A**usgabe
- Kommandozeile = Ein- und Ausgabe, der PC macht die Verarbeitung
- Admins und Entwickler:innen nutzen sie täglich

| Kanal | Kurz | Richtung | Standard |
|-------|------|----------|----------|
| Standard Input | **stdin** | Eingabe ins Programm | Tastatur |
| Standard Output | **stdout** | Ausgabe vom Programm | Bildschirm |

---

## Ausgabe mit print()

```python
print("Hallo Welt!")
print(100)
print(5 * 7)
print("Hello", "World")    # mehrere Werte mit Komma → Leerzeichen dazwischen
```

- Jedes `print()` endet standardmässig mit einer **neuen Zeile**
- Strings stehen immer in **Anführungszeichen**, sonst interpretiert Python es als Code:
  - `Hello` → Fehler
  - `"Hello"` → korrekt

### Erweiterte Steuerung: sep und end

| Parameter | Bedeutung | Standard |
|-----------|-----------|----------|
| `sep` | Trennzeichen zwischen den Elementen | Leerzeichen |
| `end` | Abschluss der Ausgabe | Zeilenumbruch `\n` |

```python
print("Hello", "World", sep=", ", end="")
print("!")                        # Hello, World!

print("He", "llo", sep="")        # Hello
print("Hallo", "Welt", sep="_")   # Hallo_Welt
```

---

## Eingabe mit input()

`input()` hält das Programm an, wartet auf Text und Enter.

```python
print(input())

mein_name = input("Wie ist dein Name? ")   # Nachricht als Argument
print("Hallo,", mein_name + "!")
```

- Die Nachricht im Argument sagt dem Benutzer, was erwartet wird
- Die Antwort wird in einer **Variable** gespeichert

### Zahlen eingeben

`input()` liefert **immer** einen String.

```python
age_str = input("Bitte gib dein Alter ein: ")
print(type(age_str))           # <class 'str'>

age = int(age_str)             # umwandeln
age_next_year = age + 1
print("Alter nächstes Jahr: " + str(age_next_year))   # für + mit String zurück zu str

# direkt bei der Eingabe umwandeln
age = int(input("Bitte gib dein Alter ein: "))
```

- `int()` für ganze Zahlen, `float()` für Kommazahlen
- Verketten mit `+` geht nur String + String, daher `str()`
- Mit f-Strings ist das Umwandeln nicht nötig: `print(f"Alter: {age}")`

---

## Verknüpfungen

→ [[02 - Variablen und Datentypen]]
→ [[03 - Mathematische Operatoren]]
→ [[10 - Characters und Strings]]
