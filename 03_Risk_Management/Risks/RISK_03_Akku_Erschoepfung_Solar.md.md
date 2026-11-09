---
id: RISK_03
type: Risk
title: Akku-Erschöpfung durch unzureichende Solar-Ladeleistung
category: Technische Risiken
probability: 0.25
impact_cost: 300
emv: 75
risk_owner: "[[00_Meta/Team/Ines Lassoued]]"
status: Active
project: "[[00_Meta/Smart Waste]]"
related_wp: "[[02_WBS_Planning/WP_4.1_Funktionstest_Hardware]]"
---

# RISK_03: Akku-Erschöpfung durch unzureichende Solar-Ladeleistung

### Ursache
Langanhaltende Schlechtwetterphasen im Winter/Herbst in Kombination mit zu hoher Sendehäufigkeit der Sensorik (kein optimaler Deep-Sleep-Modus).

### Auswirkung
Ausfall von Sensorknoten im Feldtest; Füllstände werden nicht mehr erfasst und Mülltonnen laufen unbemerkt über.

### Präventivmaßnahme (Preventive Action)
Konsequente Optimierung des ESP32 Deep-Sleep-Modus (Aufwachen nur alle 30–60 Minuten) sowie Überdimensionierung der Akkukapazität.

### Korrekturmaßnahme (Corrective Action)
Dynamische Anpassung der Sendeintervalle in Abhängigkeit von der aktuellen Akkuspannung (z. B. Reduktion auf 1 Messung pro Tag bei niedriger Spannung).