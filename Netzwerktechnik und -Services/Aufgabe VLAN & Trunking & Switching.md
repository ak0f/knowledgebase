# Lab – VLAN & Trunking & Switching

**Übung:** VLAN_Trunking_Switch_Switch.pkt (Trunking mit 802.1Q)
**Grundlagen:** [[VLAN Grundlagen]]

In dieser Übung habe ich VLANs erstellt und benannt, Ports VLANs zugewiesen, einen Trunk konfiguriert, die Kommunikation getestet und Hosts zwischen VLANs verschoben.

## Ausgangslage

| Gerät | IP-Adresse |
|-------|------------|
| PC0 | 192.168.1.20/24 |
| PC1 | 192.168.1.30/24 |
| Switch_A (VLAN 1) | 192.168.1.2/24 |
| Switch_B (VLAN 1) | 192.168.1.3/24 |

| VLAN | Name | Ports |
|------|------|-------|
| VLAN 1 | Native | Fa0/2 – 0/3 |
| VLAN 10 | Accounting | Fa0/4 – 0/6 |
| VLAN 20 | Marketing | Fa0/7 – 0/9 |
| VLAN 30 | Engineering | Fa0/10 – 0/12 |

Fa0/1 ist der Trunk zwischen den beiden Switches.

---

## Teil A – Grundkonfiguration und Ausgangslage

### Schritt 1 – Konfigurieren des Switches

Management-IP in VLAN 1 (Beispiel Switch_A):

```
Switch_A(config)# interface vlan 1
Switch_A(config-if)# ip address 192.168.1.2 255.255.255.0
Switch_A(config-if)# no shutdown
```

### Schritt 2 – Konfigurieren der Hosts

PC0 192.168.1.20/24 und PC1 192.168.1.30/24 statisch eingetragen.

### Schritt 3 – Überprüfen der Konnektivität

* **Waren die Ping-Tests erfolgreich?** Nein, die Requests waren «Timed Out».

* **Fehlerbehebung:** Ich musste die IP-Adressen bei den PCs statisch eintragen (192.168.1.20 und .30), weil DHCP fehlschlug. Ausserdem musste ich die Verbindung zwischen Switch_A und B mit `interface FastEthernet0/1` und `switchport mode trunk` als Trunk konfigurieren.

### Schritt 4 – Anzeigen der VLAN-Schnittstelleninformationen

```
Switch_A# show vlan
```

Zu Beginn gibt es nur VLAN 1 und die Standard-VLANs (1002 und folgende). Andere VLANs würde ich mit `no vlan <ID>` löschen.

---

## Teil B – VLANs erstellen und Ports zuordnen

### Schritte 5 bis 8 – VLANs erstellen und Ports zuordnen

```
Switch_A# configure terminal
Switch_A(config)# vlan 10
Switch_A(config-vlan)# name Accounting
Switch_A(config-vlan)# vlan 20
Switch_A(config-vlan)# name Marketing
Switch_A(config-vlan)# vlan 30
Switch_A(config-vlan)# name Engineering
Switch_A(config-vlan)# exit

Switch_A(config)# interface range fastethernet 0/4-6
Switch_A(config-if-range)# switchport mode access
Switch_A(config-if-range)# switchport access vlan 10

Switch_A(config-if-range)# interface range fastethernet 0/7-9
Switch_A(config-if-range)# switchport mode access
Switch_A(config-if-range)# switchport access vlan 20

Switch_A(config-if-range)# interface range fastethernet 0/10-12
Switch_A(config-if-range)# switchport mode access
Switch_A(config-if-range)# switchport access vlan 30
Switch_A(config-if-range)# end
```

Mit `show vlan` kontrolliere ich, ob alle VLANs richtig erstellt wurden.

### Schritt 9 – VLANs auf Switch_B

Dieselben Befehle wie bei Switch_A, auch auf Switch_B.

### Schritt 10 – Anzeigen der VLAN-Schnittstelleninformationen

* **Sind die Ports 0/10 bis 0/12 jetzt VLAN 30 zugeordnet?** Ja, sie werden in der Tabelle beim VLAN 30 (Engineering) angezeigt.

### Schritt 11 – Testen der VLANs

* **War der Ping-Test erfolgreich (PC zu PC)?** Nein.

* **Welches sind die Gründe dafür?** Die Verbindung zwischen den Switches war noch kein Trunk-Port. Der Switch hat die Daten vom VLAN 30 nicht an den anderen Switch weitergeleitet.

* **War der Ping-Test erfolgreich (PC zu Switch_A)?** Nein.

* **Welches sind die Gründe dafür?** Der PC ist im VLAN 30 und die IP-Adresse vom Switch ist im VLAN 1. Ohne Router können zwei verschiedene VLANs nicht miteinander kommunizieren.

---

## Teil C – Trunk einrichten und testen

### Schritt 12 – Erstellen des Trunks

Auf Switch_A und Switch_B an Fa0/1:

```
Switch_A(config)# interface fastethernet 0/1
Switch_A(config-if)# switchport mode trunk
Switch_A(config-if)# end
```

Die Switches unterstützen nur 802.1Q, deshalb muss ich die Kapselung nicht angeben.

### Schritt 13 – Überprüfen des Trunks

```
Switch_A# show interface fastethernet 0/1 switchport
```

* **Welche Trunking-Kapselung wird in der Ausgabe angezeigt?** Es wird `802.1Q` angezeigt.

### Schritt 14 – Testen der VLANs und des Trunks

* **War der Ping-Test erfolgreich (PC zu PC)?** Ja.

* **Welches sind die Gründe dafür?** Der Trunk-Port zwischen den Switches ist jetzt aktiv und transportiert die Daten vom VLAN 30 erfolgreich zum anderen Switch.

* **War der Ping-Test erfolgreich (PC zu Switch_A)?** Nein.

* **Welches sind die Gründe dafür?** Der PC ist immer noch im VLAN 30 und der Switch im VLAN 1. Sie sind in unterschiedlichen Netzwerken.

---

## Teil D – Hosts verschieben und Auswirkungen beobachten

### Schritt 16 – Testen der VLANs und des Trunks (Host verschoben)

PC0 ist von Port 0/12 auf Port 0/8 umgesteckt.

* **War der Ping-Test erfolgreich (PC0 zu PC1)?** Nein.

* **Welches sind die Gründe dafür?** PC0 ist jetzt an Port 0/8 (VLAN 20) und PC1 ist noch im VLAN 30. Unterschiedliche VLANs können sich nicht pingen.

* **War der Ping-Test erfolgreich (PC0 zu Switch_A)?** Nein.

* **Welches sind die Gründe dafür?** PC0 ist im VLAN 20 und der Switch im VLAN 1.

### Schritt 18 – Testen der VLANs und des Trunks (Zweiter Host verschoben)

PC1 ist von Port 0/12 auf Port 0/7 (Switch_B) umgesteckt.

* **War der Ping-Test erfolgreich (PC0 zu PC1)?** Ja.

* **Welches sind die Gründe dafür?** Beide PCs sind jetzt im selben VLAN (VLAN 20) und der Trunk funktioniert.

### Schritt 20 – Testen der VLANs und des Trunks (Host ins VLAN 1 verschoben)

PC0 ist von Port 0/8 auf Port 0/2 umgesteckt.

* **War der Ping-Test erfolgreich (PC0 zu PC1)?** Nein, weil PC0 jetzt im VLAN 1 ist und PC1 noch im VLAN 20.

* **War der Ping-Test erfolgreich (PC0 zu Switch_A)?** Ja.

* **Welches sind die Gründe dafür?** PC0 ist an Port 0/2 und damit wieder im VLAN 1. Die Management-IP von Switch_A ist auch im VLAN 1. Sie sind wieder im gleichen Netzwerk.

### Schritt 22 – Testen der VLANs und des Trunks (Zweiter Host ins VLAN 1 verschoben)

PC1 ist von Port 0/7 auf Port 0/3 (Switch_B) umgesteckt.

* **War der Ping-Test erfolgreich (PC zu PC)?** Ja.

* **Welches sind die Gründe dafür?** Beide PCs sind an den Switches wieder an Ports eingesteckt, die zum VLAN 1 gehören.

* **War der Ping-Test erfolgreich (PC zu Switch_A)?** Ja.

* **Welches sind die Gründe dafür?** Der PC und Switch_A sind beide im VLAN 1.

* **War der Ping-Test erfolgreich (PC zu Switch_B)?** Ja.

* **Welches sind die Gründe dafür?** Alle Geräte (PCs und Switches) sind jetzt im VLAN 1. Der Trunk leitet auch den Verkehr vom VLAN 1 problemlos durch.

---

## Fazit

Geräte können nur dann miteinander kommunizieren (Ping), wenn sie sich im selben VLAN befinden. Damit der Datenverkehr von mehreren verschiedenen VLANs über ein einziges Kabel zwischen zwei Switches gesendet werden kann, muss diese Leitung zwingend als Trunk (mit 802.1Q) konfiguriert sein.

---

## Wichtigste Befehle

| Befehl | Bedeutung |
|--------|-----------|
| `vlan 10` + `name Accounting` | VLAN erstellen und benennen |
| `interface range fastethernet 0/4-6` | mehrere Ports auf einmal konfigurieren |
| `switchport mode access` | Port als Access Port |
| `switchport access vlan 10` | Port dem VLAN 10 zuweisen |
| `switchport mode trunk` | Port als Trunk (802.1Q) |
| `interface vlan 1` + `ip address ...` | Management-IP des Switches |
| `show vlan` | VLANs und Port-Zuordnung anzeigen |
| `show interface fastethernet 0/1 switchport` | Modus und Kapselung eines Ports |
| `no vlan <ID>` | VLAN löschen |

---

## Transferprojekt (02_VLAN)

- [ ] Zuerst Doku: VLAN-Konzept (Kapitel 3.3) mit Namen, Zweck, Access-Ports und Trunk-Ports
- [ ] Basel: VLAN 110 und 120, Access-Ports zuweisen
- [ ] Bern: VLAN 210 und 220, Access-Ports zuweisen
- [ ] Zürich: VLAN 310 und 320, Access-Ports zuweisen
- [ ] Trunk zwischen Standort-Switch und Router
- [ ] Router-Subinterfaces mit Beschreibung, Interfaces aktiv
- [ ] Kontrolle: `show vlan brief`, `show interfaces trunk`, `show ip interface brief`, Ping zum Gateway
- [ ] Datei als `02_VLAN_Name.pkt` speichern
