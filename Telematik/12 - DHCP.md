# DHCP

**Fach:** Telematik
**Tags:** #DHCP #DORA #Lease #APIPA #ipconfig

---

## Lernziele

- [ ] Erklären weshalb man DHCP braucht
- [ ] Was ein DHCP-Server verteilt
- [ ] Ablauf **DORA** erklären
- [ ] Lease und Renew erklären
- [ ] Die «drei Dinge» (Broadcast, ein Server pro Subnetz, APIPA) kennen
- [ ] Mit `ipconfig` die erhaltene Konfiguration prüfen

---

## Weshalb DHCP? (4 Probleme mit statischen Adressen)

1. Jedes Gerät muss **von Hand** konfiguriert werden
2. **Begrenzter Adressraum**: freie Adressen sollen wiederverwendet werden
3. **Wechselnde Clients**: Notebooks und Handys kommen und gehen ständig
4. Keine zentrale Kontrolle, wer welche IP erhält

---

## Was verteilt ein DHCP-Server?

- **IP-Adresse**
- **Subnetzmaske**
- häufig zusätzlich: **Standard-Gateway**, **DNS-Server** und weitere Optionen

---

## DORA – der Ablauf

| Schritt | Von | Bedeutung |
|---------|-----|-----------|
| **D**iscover | Client | «Gibt es einen DHCP-Server?» (**Broadcast**, Client hat noch keine IP) |
| **O**ffer | Server | bietet eine Adresse an |
| **R**equest | Client | nimmt das Angebot an / fragt die Adresse an |
| **A**cknowledge | Server | bestätigt |

---

## Lease

Die Adresse ist nur **geliehen**.

- Der Server sagt, wie lange die Adresse gilt (**Lease-Zeit**)
- **Renew:** nach der **halben Zeit** fragt der Client nach Verlängerung
- **Release:** gibt der Client die Adresse zurück, wird sie wieder frei

So bleiben Adressen im Umlauf, statt für immer belegt zu sein.

---

## Achtung: drei Dinge

1. **Broadcast bleibt im eigenen Netz** – ein Router leitet ihn nicht automatisch weiter
2. **Ein DHCP-Server pro Subnetz** – mehrere Server synchronisieren sich nicht
3. **Kein Server erreichbar? APIPA** – der Client vergibt sich selbst eine Adresse `169.254.x.x` = es gibt keine Verbindung zum DHCP-Server

---

## Überprüfung beim Client

```bash
ipconfig         # IP-Adresse, Subnetzmaske und Gateway
ipconfig /all    # zusätzlich DHCP-Server, Lease-Zeiten und DNS-Server
```

---

## Verknüpfungen

→ [[07 - IPv4 und CIDR]]
→ [[11 - DNS]]
→ [[17 - Analysetools]]
→ [[00 - MOC]]
