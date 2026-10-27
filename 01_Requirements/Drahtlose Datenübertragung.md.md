---
id: REQ_05
type: Requirement
subtype: Functional
component: Hardware
priority: High
status: Draft
assigned_to: "[[Onat Özcelik]]"
parent: "[[Smart Waste]]"
project: "[[Smart Waste]]"
---

### Beschreibung
Das System MUSS dem Mikrocontroller die Möglichkeit bieten, die gesammelten Füllstandsdaten drahtlos an das zentrale Backend zu übertragen.

### Akzeptanzkriterien
- Der Mikrocontroller wählt sich erfolgreich in ein verfügbares Test-WLAN (oder LoRaWAN-Netzwerk) ein.
- Ein im seriellen Monitor verifizierter Messwert taucht innerhalb von 5 Sekunden als HTTP-POST- oder MQTT-Nachricht korrekt im Backend/Datenbank auf.