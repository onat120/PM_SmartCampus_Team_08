---
id: RISK_02
type: Risk
title: WLAN-Funklöcher auf dem HFU-Campusgelände
category: Externe Risiken
probability: 0.40
impact_cost: 250
emv: 100
risk_owner: "[[00_Meta/Team/Khaoula Smida]]"
status: Active
project: "[[00_Meta/Smart Waste]]"
related_wp: "[[02_WBS_Planning/WP_2.3_Anpassung_Sensorik]]"
---

# RISK_02: WLAN-Funklöcher auf dem Campus

### Ursache
Abschirmung durch Müllbehälter-Standorte in Nischen, Kellerbereichen oder hinter dichten Gebäudemauern des HFU-Campus.

### Auswirkung
Messwerte werden vom ESP32 nicht zeitnah an die Backend-API (WP 3.3) übertragen; Füllstände in der Mobile App bleiben veraltet.

### Präventivmaßnahme (Preventive Action)
Vorab-Messung der WLAN-Signalstärke (RSSI) an allen geplanten Behälter-Standorten vor der endgültigen Montage.

### Korrekturmaßnahme (Corrective Action)
Implementierung eines lokalen Ringpuffers (Offline-Caching) im Flash-Speicher des ESP32, der Messdaten zwischenspeichert und bei erneutem WLAN-Empfang gebündelt sendet.