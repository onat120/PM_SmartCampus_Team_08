# Kostenplanung & Budget (BAC) – Smart Waste (Team 08)

## 1. Interne Verrechnungssätze der Projektrollen

Für die Kalkulation der Personalkosten werden realistische interne Stundensätze für die beiden Projektrollen festgelegt:

| Projektrolle | Teammitglied | Interner Verrechnungssatz | Begründung |
| :--- | :--- | :--- | :--- |
| **Projektleitung & Softwarearchitekt** | [[00_Meta/Team/Onat Özcelik]] | **140 € / h** | Steuerungs-, Architektur- und Schnittstellenverantwortung |
| **Embedded- & App-Entwickler** | [[00_Meta/Team/Ines Lassoued]] | **100 € / h** | Hardware-Integration, Firmware- und App-Entwicklung |

---

## 2. Hardware-Stückliste (BOM – Sach- & Materialkosten)

Für den Aufbau eines funktionsfähigen Prototyps (inkl. Reserve-Sensorik für den Campus-Feldtest) fallen folgende Materialkosten an:

| Komponente | Menge | Einzelpreis | Gesamtpreis | Zugeordnetes WP |
| :--- | :--- | :--- | :--- | :--- |
| ESP32-Mikrocontroller (inkl. WLAN-Modul) | 3 Stück | 15,00 € | 45,00 € | WP 2.1 |
| Ultraschallsensor (HC-SR04 / wasserdicht) | 3 Stück | 12,00 € | 36,00 € | WP 2.1 |
| Solarpanel (6V) + LiPo-Akku & Ladecontroller | 3 Sets | 28,00 € | 84,00 € | WP 2.1 |
| Wetterfestes IP65-Gehäuse, Kabel & Kleinteile | 3 Sets | 25,00 € | 75,00 € | WP 2.2 |
| Cloud-Hosting & Testserver (3 Monate Laufzeit) | 1 Pauschale | 60,00 € | 60,00 € | WP 3.3 |
| **Summe Sach- & Materialkosten** | | | **300,00 €** | |

---

## 3. Kostenübersicht nach Arbeitspaketen (Cost Baseline / BAC)

Die Personalkosten ergeben sich aus dem geplanten Aufwand ($A$ in Stunden) multipliziert mit dem internen Verrechnungssatz der zugewiesenen Rolle:

| Arbeitspaket (WP) | Zugewiesene Rolle | Aufwand $A$ [h] | Stundensatz | Personalkosten | Sachkosten | Gesamtkosten WP | Kumulierte Kosten | Bemerkungen |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **WP 1.1** Projektplanung | Projektleitung (Onat) | 20 h | 140 €/h | 2.800 € | 0 € | **2.800 €** | 2.800 € | Nur Personalkosten |
| **WP 1.2** Projektsteuerung | Projektleitung (Onat) | 30 h | 140 €/h | 4.200 € | 0 € | **4.200 €** | 7.000 € | Projektbegleitend (30d) |
| **WP 1.3** Projektabschluss | Projektleitung (Onat) | 15 h | 140 €/h | 2.100 € | 0 € | **2.100 €** | 9.100 € | Dokumentation & Abnahme |
| **WP 2.1** Beschaffung Sensorik | Embedded-Entwickler (Ines) | 12 h | 100 €/h | 1.200 € | 165 € | **1.365 €** | 10.465 € | Inkl. ESP32, Sensoren & Solar |
| **WP 2.2** Aufbau Hardware | Embedded-Entwickler (Ines) | 24 h | 100 €/h | 2.400 € | 75 € | **2.475 €** | 12.940 € | Inkl. IP65-Gehäuse & Montage |
| **WP 2.3** Anpassung Sensorik | Embedded-Entwickler (Ines) | 28 h | 100 €/h | 2.800 € | 0 € | **2.800 €** | 15.740 € | Nur Personalkosten |
| **WP 3.1** GUI Mockup | App-Entwickler (Ines) | 16 h | 100 €/h | 1.600 € | 0 € | **1.600 €** | 17.340 € | Nur Personalkosten |
| **WP 3.2** Implementierung App | App-Entwickler (Ines) | 68 h | 100 €/h | 6.800 € | 0 € | **6.800 €** | 24.140 € | Größtes Einzelarbeitspaket |
| **WP 3.3** Backend API | Softwarearchitekt (Onat) | 64 h | 140 €/h | 8.960 € | 60 € | **9.020 €** | 33.160 € | Inkl. Server- & Hostingkosten |
| **WP 4.1** Funktionstest Hardware | Embedded-Entwickler (Ines) | 16 h | 100 €/h | 1.600 € | 0 € | **1.600 €** | 34.760 € | Nur Personalkosten |
| **WP 4.2** Integrationstest System | Softwarearchitekt (Onat) | 20 h | 140 €/h | 2.800 € | 0 € | **2.800 €** | 37.560 € | Nur Personalkosten |
| **WP 4.3** Feldtest Campus | Team (Onat & Ines) | 24 h *(12h/12h)* | 120 €/h *(Ø)* | 2.880 € | 0 € | **2.880 €** | **40.440 €** | Gemeinsame Durchführung |

---

## 4. Gesamtkostenschätzung & Budgetbegründung

| Kostenbestandteil | Betrag | Anteil |
| :--- | :--- | :--- |
| **Personalkosten gesamt** (337 Personenstunden) | 40.140,00 € | 89,3 % |
| **Sach- & Materialkosten (BOM)** | 300,00 € | 0,7 % |
| **Cost Baseline / Budget at Completion (BAC)** | **40.440,00 €** | **90,0 %** |
| **Risikorückstellung (Contingency Reserve, 10 %)** | 4.044,00 € | 9,0 % |
| **Management-Reserve (Gemeinkosten / Unvorhergesehenes)** | 456,00 € | 1,0 % |
| **Gesamtprojektbudget (inkl. Reserven)** | **44.940,00 €** | **100,0 %** |

**Begründung der Schätzung:**
1. **Schwerpunkt auf Entwicklungsaufwand:** Da es sich um ein Software- und IoT-Entwicklungsprojekt handelt, entfallen rund 90 % der Basiskosten auf qualifizierte Arbeitszeit (`WP 3.2` Mobile App und `WP 3.3` Backend API bilden die größten Kostentreiber), während die Hardware-Stückliste durch günstige Standardkomponenten (ESP32) gering bleibt.
2. **Einplanung von Risikorückstellungen:** Auf Basis der Risikoanalyse aus Übung 6 (insbesondere `RISK_04` Verzögerung der App-Entwicklung mit EMV = 175 € und `RISK_01` Lieferverzug Sensorik mit EMV = 120 €) wird ein kalkulatorischer Risikopuffer von rund 10 % (4.044 €) eingeplant, um Mehraufwände bei Schnittstellentests oder Ersatzbeschaffungen abzufedern.