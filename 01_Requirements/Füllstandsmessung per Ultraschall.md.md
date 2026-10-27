---
id: REQ_01
type: Requirement
subtype: Functional
component: Hardware
priority: High
status: Draft
assigned_to: "[[Onat Özcelik]]"
parent: "[[Smart Waste.md]]"
project: "[[Smart Waste.md]]"
---

### Beschreibung
Das System MUSS der IoT-Datenbank die Möglichkeit bieten, den aktuellen Füllstand der Mülltonnen zentimetergenau zu erfassen.

### Akzeptanzkriterien
- Ein Ultraschallsensor ist im Deckel des Müllbehälters montiert.
- Der Sensor misst den Abstand zum Müll in der Tonne.
- Der gemessene Abstandswert wird korrekt in Zentimetern (cm) im seriellen Monitor oder der Datenbank ausgegeben, wobei die Abweichung max. +/- 2 cm zur physischen Messung mit dem Zollstock betragen darf.