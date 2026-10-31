# Smart Waste - KI-gestützte Netzplanrechnung (Aufgabe 5.3)

**Projektstart:** Montag, 02.11.2026  
**Arbeitszeitmodell:** 5-Tage-Woche (Mo–Fr)

## Berechnete Termintabelle

| Arbeitspaket (WP) | Dauer (D) | Frühester Beginn (FB) | Frühestes Ende (FE) | Spätester Beginn (SB) | Spätestes Ende (SE) | Gesamte Pufferzeit (GP) | Kritischer Pfad? |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **WP 1.1 Projektplanung** | 5 Tage | 02.11.2026 | 06.11.2026 | 02.11.2026 | 06.11.2026 | 0 Tage | **Ja** |
| **WP 2.1 Beschaffung Sensorik** | 9 Tage (2d+7d) | 09.11.2026 | 19.11.2026 | 10.11.2026 | 20.11.2026 | 1 Tag | **Nein** |
| **WP 2.2 Aufbau Hardware** | 5 Tage | 20.11.2026 | 26.11.2026 | 23.11.2026 | 27.11.2026 | 1 Tag | **Nein** |
| **WP 2.3 Anpassung Sensorik** | 10 Tage | 27.11.2026 | 10.12.2026 | 30.11.2026 | 11.12.2026 | 1 Tag | **Nein** |
| **WP 3.1 GUI Mockup** | 7 Tage | 09.11.2026 | 17.11.2026 | 09.11.2026 | 17.11.2026 | 0 Tage | **Ja** |
| **WP 3.2 Implementierung App** | 15 Tage | 18.11.2026 | 08.12.2026 | 18.11.2026 | 08.12.2026 | 0 Tage | **Ja** |
| **WP 3.3 Backend API** | 12 Tage | 18.11.2026 | 03.12.2026 | 23.11.2026 | 08.12.2026 | 3 Tage | **Nein** |
| **WP 4.1 Funktionstest Hardware** | 4 Tage | 11.12.2026 | 16.12.2026 | 14.12.2026 | 17.12.2026 | 1 Tag | **Nein** |
| **WP 4.2 Integrationstest System** | 5 Tage | 17.12.2026 | 23.12.2026 | 17.12.2026 | 23.12.2026 | 0 Tage | **Ja** |
| **WP 4.3 Feldtest Campus** | 7 Tage | 24.12.2026 | 05.01.2027 | 24.12.2026 | 05.01.2027 | 0 Tage | **Ja** |
| **WP 1.3 Projektabschluss** | 10 Tage | 06.01.2027 | 19.01.2027 | 06.01.2027 | 19.01.2027 | 0 Tage | **Ja** |

---

## Auswertung
* **Kritischer Pfad:** `WP 1.1 -> WP 3.1 -> WP 3.2 -> WP 4.2 -> WP 4.3 -> WP 1.3`
* **Gesamtdauer:** 49 Arbeitstage
* **Geplantes Projektende:** Dienstag, 19.01.2027

---

## KI-Audit Feedback

### 1. Logische Zyklen & Struktur
* **Befund:** Der Netzplan ist frei von zirkulären Abhängigkeiten. Der Fluss verläuft strikt von Start zu Ende.

### 2. Hardware-Verfügbarkeit & Lieferketten-Risiko
* **Befund:** Die Beschaffung (`WP 2.1`) inklusive der 7-tägigen Lead Time hat aktuell 1 Tag Puffer und liegt *nicht* auf dem kritischen Pfad.
* **Risiko:** Wenn sich die Lieferung der Ultraschallsensoren um mehr als 1 Tag verzögert, rutscht der gesamte Hardware-Strang auf den kritischen Pfad und verschiebt das Projektende.

### 3. Engpässe auf dem kritischen Pfad
* **Hauptengpass:** Der Software-Strang um `WP 3.2 Implementierung App` (15 Tage Dauer) bestimmt maßgeblich die Gesamtprojektdauer.
* **Verbesserungspotenzial:** Frühe Modultests oder der Einsatz von Mock-Schnittstellen während der App-Entwicklung können das Risiko auf dem kritischen Pfad minimieren.