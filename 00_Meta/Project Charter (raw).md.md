TP 08: Smart Waste (Intelligentes Müll- und Recycling-Management)
Das Teilprojekt digitalisiert das Entsorgungs- und Recyclingmanagement des Campus-
Betriebshofs. Ultraschallsensoren in den Müllbehältern ermitteln kontinuierlich Füllstände,
während Neigungssensoren Vandalismus oder Umkippen melden. Das Reinigungspersonal
nutzt eine Mobile App zur Anzeige optimierter Abholrouten, Füllstandswarnungen und zur
Konfiguration von Sensor-Grenzwerten.

- Hardware: Ultraschall-Füllstandssensoren in Tonnen, GPS-Module, Neigungssensoren (Feuer/Vandalismus). 
- Software: Mobile App zur Routenoptimierung für den Campus-Betriebshof, LiveFüllstandsanzeige und Darstellung von Recycling-Statistiken.

# Rohfassung Project Charter - TP 08: Smart Waste

- **Projektname:** Intelligente / Smarte Abfallwirtschaft (Smart Waste Management)
- **Projektidee & Grundkonzept:** 
  - Ausstattung von Abfallbehältern auf dem HFU-Campus mit IoT-Sensorik zur kontinuierlichen Füllstandsmessung.
  - Das System bewertet autonom, ob eine Behälterleerung am aktuellen Tag erforderlich ist.
  - Stromversorgung der Hardware-Komponenten vor Ort vorzugsweise autark über integrierte Solar-Panels und Energiespeicher.
  - Durchführung automatisierter Scans/Messungen mehrmals täglich.
  - Generierung optimierter Abholrouten für das Reinigungspersonal (analog zum Logistik-System der Deutschen Post) inkl. Push-Benachrichtigungen in der Mobile App.
  - Statusabgleich abgeholter Behälter manuell per App oder automatisch über Sensor-Feedback nach der Leerung.
- **Optionale Erweiterung ** 
  - Anbindung von Mechanismen oder Sensoren zur verfeinerten Mülltrennung.
- **Zielgruppe & Stakeholder:** 
  - Campus-Betriebshof, Reinigungspersonal, Studierende und Lehrende an der HFU.
- **Hardware (Klassisches PM):** 
  - Ultraschall-Füllstandssensoren, GPS-Module für Standortverortung, kleine Solar-Charge-Controller & Akku-Puffer, Mikrocontroller (z. B. ESP32).
- **Software & App (Agiles PM):** 
  - Mobile App für Reinigungskräfte & Betriebshof mit Live-Füllstandsanzeige, Routenoptimierung, Anpassung von Warnschwellen und Recycling-Statistiken.
- **Schnittstellen & Restriktionen:** 
  - REST-API für Datenaustausch zwischen Sensorik und App.
  - Vorerst Beschränkung auf einen prototypischen Pilotbetrieb auf dem Campusgelände.
- **Zukunftsvision (Out-of-Scope für aktuelle Phase):** 
  - Vollautomatisierte Leerung durch autonome Roboter oder Müllfahrzeuge (auf Abruf / On-Demand-Systeme).
  - Unterirdische vernetzte Rohrsammelsysteme und direkte Dezentral-Energiegewinnung vor Ort.