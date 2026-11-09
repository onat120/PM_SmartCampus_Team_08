# Risk Breakdown Structure (RBS) - Smart Waste

## Risiko-Strukturbaum

```mermaid
graph LR
    Root[Smart Waste Teilprojekt] --> Cat1[1. Technische Risiken]
    Root --> Cat2[2. Externe Risiken]
    Root --> Cat3[3. Organisatorische Risiken]
    Root --> Cat4[4. Projektmanagement-Risiken]

    %% 1. Technische Risiken
    Cat1 --> R11[1.1 Hardware: Sensor-Defekt / Feuchtigkeitsschaden]
    Cat1 --> R12[1.2 Software: MQTT-Timeout / Verbindungsabbruch]
    Cat1 --> R13[1.3 Security: Unverschlüsselte Datenübertragung]

    %% 2. Externe Risiken
    Cat2 --> R21[2.1 Lieferkette: Sensoren-Lieferverzug > 14 Tage]
    Cat2 --> R22[2.2 Infrastruktur: WLAN-Funklöcher am Campus]
    Cat2 --> R23[2.3 Compliance: DSGVO-Konflikt bei Standortdaten]

    %% 3. Organisatorische Risiken
    Cat3 --> R31[3.1 Team: Krankheitsbedingter Ausfall Teammitglied]
    Cat3 --> R32[3.2 Know-how: Einarbeitungsverzögerung Obsidian / Git]

    %% 4. Projektmanagement-Risiken
    Cat4 --> R41[4.1 Schätzung: Unterschätzter Aufwand Backend-API]
    Cat4 --> R42[4.2 Termin: Kritischer Pfad App-Entwicklung ohne Puffer]
    Cat4 --> R43[4.3 Qualität: Feldtest-Verzögerung durch Prüfungsphase]
```

---

## Übersicht der Risikokategorien

| ID | Kategorie | Beschreibung |
| :--- | :--- | :--- |
| **1.x** | **Technische Risiken** | Risiken bezüglich Sensorik, Hardware-Korrosion, API-Schnittstellen und Datensicherheit. |
| **2.x** | **Externe Risiken** | Lieferverzögerungen von Bauteilen, WLAN-Abdeckung der Hochschule und rechtliche Vorgaben. |
| **3.x** | **Organisatorische Risiken** | Personalausfälle im Team 08 sowie Einarbeitung in benötigte Software-Tools. |
| **4.x** | **PM-Risiken** | Fehleinschätzungen bei Aufwänden, Pufferknappheit auf dem kritischen Pfad und Terminkonflikte. |