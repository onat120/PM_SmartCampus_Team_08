# Ressourcenplanung – Smart Waste (Team 08)

## 1. Teamrollen & Verfügbare Kapazitäten (K)

Für das Projekt **Smart Waste** stehen zwei Teammitglieder zur Verfügung (5-Tage-Woche, Projektstart: 02.11.2026):

| Rolle | Teammitglied | Wochenkapazität | Tageskapazität (K) | Aufgabenbereich |
| :--- | :--- | :--- | :--- | :--- |
| **Projektleitung & Softwarearchitekt** | [[00_Meta/Team/Onat Özcelik]] | 25 h / Woche | 5,0 h / Tag | Projektsteuerung, Planung, Backend-API, Systemtests |
| **Embedded- & App-Entwickler** | [[00_Meta/Team/Ines Lassoued]] | 20 h / Woche | 4,0 h / Tag | Sensorik, ESP32-Firmware, UI/UX & Mobile App |

---

## 2. Rollenzuweisung & Dauerberechnung (D = A / K)

Die Dauer in Arbeitstagen (D) berechnet sich aus dem geschätzten Aufwand (A in Stunden) geteilt durch die Tageskapazität (K):

| Arbeitspaket (WP) | Zugewiesene Rolle | Aufwand A [h] | Kapazität K [h/Tag] | Berechnete Dauer (D) | Geplante Dauer |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **WP 1.1** Projektplanung | Projektleitung (Onat) | 20 h | 4,0 h/Tag | 5,0 Tage | **5 Tage** |
| **WP 1.2** Projektsteuerung | Projektleitung (Onat) | 30 h | 1,0 h/Tag *(begleitend)* | 30,0 Tage | **30 Tage** *(projektbegleitend)* |
| **WP 1.3** Projektabschluss | Projektleitung (Onat) | 15 h | 2,0 h/Tag | 7,5 Tage | **8 Tage** |
| **WP 2.1** Beschaffung Sensorik | Embedded-Entwickler (Ines) | 12 h | 3,0 h/Tag | 4,0 Tage | **4 Tage** *(+ 7d Lieferzeit)* |
| **WP 2.2** Aufbau Hardware | Embedded-Entwickler (Ines) | 24 h | 4,0 h/Tag | 6,0 Tage | **6 Tage** |
| **WP 2.3** Anpassung Sensorik | Embedded-Entwickler (Ines) | 28 h | 3,0 h/Tag | 9,33 Tage | **10 Tage** |
| **WP 3.1** GUI Mockup | App-Entwickler (Ines) | 16 h | 3,0 h/Tag | 5,33 Tage | **6 Tage** |
| **WP 3.2** Implementierung App | App-Entwickler (Ines) | 68 h | 4,5 h/Tag | 15,11 Tage | **15 Tage** |
| **WP 3.3** Backend API | Softwarearchitekt (Onat) | 64 h | 5,5 h/Tag | 11,64 Tage | **12 Tage** |
| **WP 4.1** Funktionstest Hardware | Embedded-Entwickler (Ines) | 16 h | 4,0 h/Tag | 4,0 Tage | **4 Tage** |
| **WP 4.2** Integrationstest System | Softwarearchitekt (Onat) | 20 h | 4,0 h/Tag | 5,0 Tage | **5 Tage** |
| **WP 4.3** Feldtest Campus | Team (Onat & Ines) | 24 h | 3,5 h/Tag | 6,86 Tage | **7 Tage** |


## 3. Terminplan (Gantt-Chart)

Das folgende Gantt-Chart zeigt die zeitliche Abfolge aller Arbeitspakete ab dem Projektstart am **02.11.2026** (basierend auf der berechneten Dauer $D$ und den Abhängigkeiten aus der Ablaufplanung):

```mermaid
gantt
    title Projektterminplan – Smart Waste (Team 08)
    dateFormat YYYY-MM-DD
    excludes weekends

    section 1. Projektmanagement
    WP 1.1 Projektplanung           :a1, 2026-11-02, 5d
    WP 1.2 Projektsteuerung         :active, a2, 2026-11-09, 30d
    WP 1.3 Projektabschluss         :a3, after t3, 8d

    section 2. Hardware & Sensorik
    WP 2.1 Beschaffung Sensorik     :h1, after a1, 4d
    Lead Time Lieferung (Puffer)    :crit, h1_wait, after h1, 7d
    WP 2.2 Aufbau Hardware          :h2, after h1_wait, 6d
    WP 2.3 Anpassung Sensorik       :h3, after h2, 10d

    section 3. Software & App
    WP 3.1 GUI Mockup               :s1, after a1, 6d
    WP 3.2 Implementierung App      :s2, after s1, 15d
    WP 3.3 Backend API              :s3, after a1, 12d

    section 4. Test & Inbetriebnahme
    WP 4.1 Funktionstest Hardware   :t1, after h3, 4d
    WP 4.2 Integrationstest System  :t2, after s2, 5d
    WP 4.3 Feldtest Campus          :t3, after t1 t2, 7d
````

**Erläuterung zum Terminplan:**

- **Parallelisierung:** Während die Hardware-Komponenten bestellt werden und die Lieferzeit (_Lead Time_, 7 Tage) läuft, startet parallel die Softwareentwicklung (`WP 3.1` GUI Mockup und `WP 3.3` Backend API).
    
- **Kritischer Pfad & Puffer:** Die Lieferzeit in `WP 2.1` bildet einen zeitlichen Puffer für die Hardware-Stränge. Der Integrationstest (`WP 4.2`) und der abschließende Feldtest auf dem HFU-Campus (`WP 4.3`) bündeln Hardware- und Software-Ergebnisse.

## 4. Belastungsdiagramm (Ressourcenhistogramm)

Die folgende Übersicht stellt den wöchentlichen Stundenbedarf der verfügbaren Maximal-Kapazität von **Onat Özcelik (max. 25 h/Woche)** und **Ines Lassoued (max. 20 h/Woche)** gegenüber:

|**Projektwoche (KW)**|**Zeitraum**|**Bedarf Onat [h]**|**Max. Kapazität Onat**|**Auslastung Onat**|**Bedarf Ines [h]**|**Max. Kapazität Ines**|**Auslastung Ines**|**Konflikt-Check**|
|---|---|---|---|---|---|---|---|---|
|**Woche 1** (KW 45)|02.11. – 06.11.2026|20 h _(WP 1.1)_|25 h|80 %|0 h _(Vorbereitung)_|20 h|0 %|OK (Keine Überlast)|
|**Woche 2** (KW 46)|09.11. – 13.11.2026|22 h _(WP 1.2 + 3.3)_|25 h|88 %|18 h _(WP 2.1 + 3.1)_|20 h|90 %|OK (Keine Überlast)|
|**Woche 3** (KW 47)|16.11. – 20.11.2026|23 h _(WP 1.2 + 3.3)_|25 h|92 %|15 h _(WP 3.1 + 3.2)_|20 h|75 %|OK (Lieferzeit WP 2.1)|
|**Woche 4** (KW 48)|23.11. – 27.11.2026|17 h _(WP 1.2 + 3.3)_|25 h|68 %|20 h _(WP 2.2 + 3.2)_|20 h|100 %|OK (Vollauslastung Ines)|
|**Woche 5** (KW 49)|30.11. – 04.12.2026|5 h _(WP 1.2)_|25 h|20 %|20 h _(WP 2.3 + 3.2)_|20 h|100 %|OK (Vollauslastung Ines)|
|**Woche 6** (KW 50)|07.12. – 11.12.2026|5 h _(WP 1.2)_|25 h|20 %|19 h _(WP 2.3 + 4.1)_|20 h|95 %|OK (Keine Überlast)|
|**Woche 7** (KW 51)|14.12. – 18.12.2026|25 h _(WP 1.2 + 4.2)_|25 h|100 %|12 h _(WP 4.1 + 4.3)_|20 h|60 %|OK (Vollauslastung Onat)|
|**Woche 8** (KW 52)|21.12. – 25.12.2026|15 h _(WP 4.3 + 1.3)_|25 h|60 %|12 h _(WP 4.3)_|20 h|60 %|OK (Keine Überlast)|
|**Woche 9** (KW 53)|28.12. – 01.01.2027|10 h _(WP 1.3)_|25 h|40 %|0 h|20 h|0 %|OK (Projektabschluss)|

**Fazit zur Ressourcenauslastung:** Durch die geschickte Parallelisierung von Hardware-Lieferzeit (`WP 2.1`) und Software-Entwicklung (`WP 3.1`/`3.2`) überschreitet kein Teammitglied seine wöchentliche Maximalkapazität (max. 100 % Auslastung, **keine Ressourcenkonflikte**)