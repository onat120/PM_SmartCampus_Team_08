---
id: REQ_02
type: Requirement
subtype: Constraint
component: Hardware
priority: High
status: Draft
assigned_to: "[[Onat Özcelik]]"
parent: "[[Smart Waste]]"
project: "[[Smart Waste]]"
---

### Beschreibung
Der Sensorknoten MUSS zwingend autark über ein integriertes Solar-Panel mit Akku betrieben werden, ohne an das lokale Stromnetz des Campus angeschlossen zu sein.

### Akzeptanzkriterien
- Das System ist ausschließlich mit dem Akku und dem Solar-Panel verbunden.
- Ein Testlauf von 7 aufeinanderfolgenden Tagen im Freien zeigt, dass das System durchgehend Messwerte sendet.
- Die Akkuspannung fällt dabei nicht unter die kritische Betriebsspannung des Mikrocontrollers (z. B. 3,3 V).