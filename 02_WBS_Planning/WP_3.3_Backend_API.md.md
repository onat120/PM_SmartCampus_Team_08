---
id: WP_3.3
type: Work Package
category: Software
estimated_effort: 64
owner: "[[Onat Özcelik]]"
status: Planned
parent: "[[Smart Waste]]"
project: "[[Smart Waste]]"
duration_days: 12
lead_time_days: 0
pert_optimistic: 60
pert_likely: 64
pert_pessimistic: 70
pert_estimated_effort: 64.33
pert_sigma: 1.67
---
## Risiko-Interpretation
**Pessimistischer Wert (P):** Die Anbindung an die zentrale Hochschul-Datenbank könnte durch fehlerhafte API-Dokumentationen oder Server-Restriktionen länger dauern als geplant.
**Risiko-Monitoring:** Das mittlere Risiko ($\sigma=1{,}67$) erfordert frühe Integrationstests mit Dummy-Daten, um Schnittstellenprobleme aufzudecken, bevor die echte Hardware angebunden wird.
### Beschreibung
Aufbau der Backend-Infrastruktur (REST-API / MQTT-Broker) und Anlegen der Datenbank zur Speicherung der Sensorwerte und Routendaten.

### Abnahmekriterium
Das Backend nimmt Messwerte via REST-API entgegen, speichert diese in der Datenbank und stellt Endpunkte für die Mobile App bereit.