# Standard In / Standard Out

**Modul:** Einstieg Programmieren (BE2026 PE)
**Tags:** #Python #stdin #stdout #print #input #EVA

---

## Kommandozeile und EVA

- Die Kommandozeile war die erste Schnittstelle zwischen Mensch und Computer (vor GUI und Maus)
- **EVA-Prinzip:** Eingabe → Verarbeitung → Ausgabe

| Kanal | Kurz | Standard |
|-------|------|----------|
| Standard Input | **stdin** | Tastatur |
| Standard Output | **stdout** | Bildschirm |

---

## print()

```python
print("Hallo Welt!")
print(5 * 7)
print("Hello", "World")     # mehrere Werte mit Komma
```

- Jedes `print()` endet standardmässig mit einer neuen Zeile
- Strings immer in Anführungszeichen, sonst denkt Python es ist Code

| Parameter | Bedeutung | Standard |
|-----------|-----------|----------|
| `sep` | Trennzeichen zwischen den Werten | Leerzeichen |
| `end` | Abschluss der Ausgabe | Zeilenumbruch |

```python
print("Hello", "World", sep=", ", end="")
print("!")                       # Hello, World!
print("He", "llo", sep="")       # Hello
```

---

## input()

Hält das Programm an und wartet auf Text + Enter. Die Nachricht im Argument sagt dem Benutzer, was er eingeben soll.

```python
name = input("Wie ist dein Name? ")
print("Hallo,", name + "!")
```

**Zahlen:** `input()` gibt immer einen String.

```python
age = int(input("Alter: "))
print("Nächstes Jahr: " + str(age + 1))    # + braucht String, darum str()
print(f"Nächstes Jahr: {age + 1}")         # f-String braucht kein str()
```

---

→ [[02 - Variablen und Datentypen]] · [[03 - Mathematische Operatoren]] · [[10 - Characters und Strings]]
