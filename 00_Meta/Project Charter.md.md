---
id: PC_08
type: Project Charter
tags:
parent: "[[Smart Waste]]"
project: "[[Smart Waste]]"
---

# Projektauftrag (Project Charter) - TP 08: Smart Waste

## Projektname & Vision
Das Projekt **"Smart Waste Management"** digitalisiert und optimiert das Entsorgungs- und Recyclingmanagement auf dem HFU-Campus durch ein intelligentes IoT-Sensorsystem. Durch den Einsatz von autark solarbetriebenen Ultraschall-Füllstandssensoren in Kombination mit automatischer Datenanalyse werden Müllbehälter bedarfsgerecht erfasst und Leerungen vorausschauend geplant. Die dazugehörige Mobile App versorgt das Reinigungspersonal mit dynamisch optimierten Abholrouten, reduziert unnötige Kontrollgänge und verbessert die Effizienz des Betriebshofs nachhaltig.

## Systemabgrenzung

### In-Scope (Projektumfang)
* **Hardware:**
  * Ultraschall-Sensoren zur präzisen Füllstandsmessung in Müll- und Recyclingbehältern.
  * Kompakte Solar-Panels inklusive Akku-Ladecontroller für einen autarken Betrieb der Sensorik.
  * ESP32-Mikrocontroller sowie GPS-Module zur genauen Standortverortung der Behälter.
* **Software:**
  * Mobile App für das Reinigungspersonal zur Anzeige aktueller Füllstände, Warnschwellen und Anpassung von Systemparametern.
  * Logistik-Modul zur automatischen Generierung optimierter Abholrouten (analog zum Post-Zustellprinzip).
  * Statusabgleich von Behältern (manuell in der App oder automatisch per Sensor-Feedback nach der Leerung).
  * Modulare Schnittstelle für eine spätere Mülltrennungs-Analyse.
* **Schnittstellen:** REST-API für den sicheren Datentransfer zwischen Mikrocontrollern, Datenbank und Mobile App.

### Out-of-Scope (Nicht im Projektumfang)
* Physische Müllabholung durch autonome Roboter oder automatisierte Müllfahrzeuge.
* Bau unterirdischer Rohrleitungs-Sammelsysteme oder Anlagen zur direkten Energieumwandlung vor Ort.
* Anbindung städtischer Entsorgungsbetriebe außerhalb des HFU-Campusgeländes.

## Magisches Dreieck

* **Zeit (FIX):** Der Abgabetermin am Ende des Semesters ist unumstößlich vorgegeben, da der Prototyp im Praktikum demonstriert werden muss.
* **Kosten (FIX):** Das Budget für physische Komponenten (Sensoren, Solar-Panels, Mikrocontroller) ist auf den vorgegebenen Rahmen beschränkt.
* **Scope / Qualität (VARIABEL):** Der Funktionsumfang der Mobile App und optionale Erweiterungen (wie die verfeinerte Analyse der Mülltrennung) können bei zeitlichen Engpässen agil skaliert oder auf nachfolgende Phasen verschoben werden.

## Kritische Erfolgsfaktoren
1. **Zuverlässige autarke Energieversorgung:** Stabile Funktion der Sensor-Knoten über Solar-Panels und Akkus.
2. **Messbare Routenoptimierung:** Nachweisbare Reduktion der Abholwege für das Reinigungspersonal um mindestens 15–20 %.
3. **Hohe Datenqualität:** Störungsfreie und korrekte Übermittlung der Füllstandsdaten via REST-API an die App.
4. **Intuitive Bedienbarkeit:** Hohe Nutzerakzeptanz der Mobile App beim Betriebshof-Personal durch eine einfache Benutzeroberfläche.