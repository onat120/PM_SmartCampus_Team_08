---
id: REQ_10
type: Requirement
subtype: Functional
component: Software
priority: Medium
status: Draft
assigned_to: "[[Ines Lassoued]]"
parent: "[[Smart Waste]]"
project: "[[Smart Waste]]"
---

### Beschreibung
Die Mobile App MUSS dem Reinigungspersonal die Möglichkeit bieten, automatische Push-Benachrichtigungen beim Erreichen eines kritischen Tonnen-Füllstands zu empfangen.

### Akzeptanzkriterien
- Wenn das Backend bei einer Tonne den Wert von 100 % registriert, wird ein Event getriggert.
- Auf dem Endgerät des Reinigungspersonals (mit installierter App) erscheint unmittelbar daraufhin eine System-Push-Benachrichtigung mit dem Inhalt "Behälter [ID/Standort] ist voll".