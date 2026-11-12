## Schritt 3 – Überprüfen der Konnektivität

* **Waren die Ping-Tests erfolgreich?** Nein, die Requests waren "Timed Out".

* **Fehlerbehebung:** Ich musste die IP-Adressen bei den PCs statisch eintragen (192.168.1.20 und .30), weil DHCP fehlschlug. Ausserdem musste ich die Verbindung zwischen Switch_A und B mit `interface FastEthernet0/1` und `switchport mode trunk` als Trunk konfigurieren.

## Schritt 10 – Anzeigen der VLAN-Schnittstelleninformationen

* **Sind die Ports 0/10 bis 0/12 jetzt VLAN 30 zugeordnet?** Ja, sie werden in der Tabelle beim VLAN 30 (Engineering) angezeigt.

## Schritt 11 – Testen der VLANs

* **War der Ping-Test erfolgreich (PC zu PC)?** Nein.

* **Welches sind die Gründe dafür?** Die Verbindung zwischen den Switches war noch kein Trunk-Port. Der Switch hat die Daten vom VLAN 30 nicht an den anderen Switch weitergeleitet.

* **War der Ping-Test erfolgreich (PC zu Switch_A)?** Nein.

* **Welches sind die Gründe dafür?** Der PC ist im VLAN 30 und die IP-Adresse vom Switch ist im VLAN 1. Ohne Router können zwei verschiedene VLANs nicht miteinander kommunizieren.

## Schritt 13 – Überprüfen des Trunks

* **Welche Trunking-Kapselung wird in der Ausgabe angezeigt?** Es wird `802.1Q` angezeigt.

## Schritt 14 – Testen der VLANs und des Trunks

* **War der Ping-Test erfolgreich (PC zu PC)?** Ja.

* **Welches sind die Gründe dafür?** Der Trunk-Port zwischen den Switches ist jetzt aktiv und transportiert die Daten vom VLAN 30 erfolgreich zum anderen Switch.

* **War der Ping-Test erfolgreich (PC zu Switch_A)?** Nein.

* **Welches sind die Gründe dafür?** Der PC ist immer noch im VLAN 30 und der Switch im VLAN 1. Sie sind in unterschiedlichen Netzwerken.

## Schritt 16 – Testen der VLANs und des Trunks (Host verschoben)

* **War der Ping-Test erfolgreich (PC0 zu PC1)?** Nein.

* **Welches sind die Gründe dafür?** PC0 ist jetzt an Port 0/8 (VLAN 20) und PC1 ist noch im VLAN 30. Unterschiedliche VLANs können sich nicht pingen.

* **War der Ping-Test erfolgreich (PC0 zu Switch_A)?** Nein.

* **Welches sind die Gründe dafür?** PC0 ist im VLAN 20 und der Switch im VLAN 1.

## Schritt 18 – Testen der VLANs und des Trunks (Zweiter Host verschoben)

* **War der Ping-Test erfolgreich (PC0 zu PC1)?** Ja.

* **Welches sind die Gründe dafür?** Beide PCs sind jetzt im selben VLAN (VLAN 20) und der Trunk funktioniert.

## Schritt 20 – Testen der VLANs und des Trunks (Host ins VLAN 1 verschoben)

* **War der Ping-Test erfolgreich (PC0 zu PC1)?** Nein, weil PC0 jetzt im VLAN 1 ist und PC1 noch im VLAN 20.

* **War der Ping-Test erfolgreich (PC0 zu Switch_A)?** Ja.

* **Welches sind die Gründe dafür?** PC0 ist an Port 0/2 und damit wieder im VLAN 1. Die Management-IP von Switch_A ist auch im VLAN 1. Sie sind wieder im gleichen Netzwerk.
## Schritt 22 – Testen der VLANs und des Trunks (Zweiter Host ins VLAN 1 verschoben)

* **War der Ping-Test erfolgreich (PC zu PC)?** Ja.

* **Welches sind die Gründe dafür?** Beide PCs sind an den Switches wieder an Ports eingesteckt, die zum VLAN 1 gehören.

* **War der Ping-Test erfolgreich (PC zu Switch_A)?** Ja.

* **Welches sind die Gründe dafür?** Der PC und Switch_A sind beide im VLAN 1.

* **War der Ping-Test erfolgreich (PC zu Switch_B)?** Ja.

* **Welches sind die Gründe dafür?** Alle Geräte (PCs und Switches) sind jetzt im VLAN 1. Der Trunk leitet auch den Verkehr vom VLAN 1 problemlos durch.
## Fazit

Geräte können nur dann miteinander kommunizieren (Ping), wenn sie sich im selben VLAN befinden. Damit der Datenverkehr von mehreren verschiedenen VLANs über ein einziges Kabel zwischen zwei Switches gesendet werden kann, muss diese Leitung zwingend als Trunk (mit 802.1Q) konfiguriert sein.