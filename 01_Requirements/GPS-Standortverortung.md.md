---
id: REQ_03
type: Requirement
subtype: Functional
component: Hardware
priority: Medium
status: Draft
assigned_to: "[[Onat Özcelik]]"
parent: "[[Smart Waste.md]]"
project: "[[Smart Waste.md]]"
---

### Beschreibung
Das System MUSS dem Administrator die Möglichkeit bieten, die exakte GPS-Position jedes nachgerüsteten Müllbehälters abzurufen.

### Akzeptanzkriterien
- Ein GPS-Modul ist an den Mikrocontroller angeschlossen.
- Die GPS-Koordinaten (Breiten- und Längengrad) werden erfolgreich in die Datenbank geschrieben.
- Die angezeigten Koordinaten weichen im Feldtest maximal 10 Meter vom tatsächlichen physischen Standort auf dem Campus ab.