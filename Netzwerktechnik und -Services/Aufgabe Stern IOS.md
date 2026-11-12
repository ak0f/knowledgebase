Aufgabe 1:
- ipconfig /all: IP: 192.168.10.11 Maske: 255.255.255.0 Gateway: 0.0.0.0 DNS-Server: 0.0.0.0
- ping gateway: OK, ping dns: OK, 
- Ausgangszustand Desktop (FastEthernet0): IP 192.168.10.11, Maske 255.255.255.0, Default Gateway 0.0.0.0 (nicht gesetzt)
- ping 192.168.10.1: 4 von 4 OK (TTL 255) -> Router im lokalen Netz erreichbar
- Hypothese: Layer 3, am Desktop fehlt das Default Gateway, daher sind Ziele ausserhalb von 192.168.10.0/24 (Internet) nicht erreichbar
- Noch zu prüfen: Gateway-IP im Wireless-Router (GUI), DNS-Server-Eintrag, ISP-Router (show ip interface brief)


Aufgabe 2: