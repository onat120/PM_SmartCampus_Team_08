```mermaid
graph LR
    M_Start([Start: Projektbeginn]) --> AP_11[WP 1.1: Projektplanung<br/>D=5d]

    %% Hardware-Strang mit Lead Time
    AP_11 --> | EA | AP_21[WP 2.1: Beschaffung Sensorik<br/>D=2d]
    AP_21 --> | EA + 7d Lead Time | AP_22[WP 2.2: Aufbau Hardware<br/>D=5d]
    AP_22 --> | EA | AP_23[WP 2.3: Anpassung Sensorik<br/>D=10d]

    %% Paralleler Software-Strang (Anfangsfolge AA)
    AP_11 --> | AA | AP_31[WP 3.1: GUI Mockup<br/>D=7d]
    AP_31 --> | EA | AP_32[WP 3.2: Implementierung App<br/>D=15d]
    AP_31 --> | EA | AP_33[WP 3.3: Backend API<br/>D=12d]

    %% Integration & Test
    AP_23 --> | EA | AP_41[WP 4.1: Funktionstest Hardware<br/>D=4d]
    AP_32 --> | EA | AP_42[WP 4.2: Integrationstest System<br/>D=5d]
    AP_33 --> | EA | AP_42
    AP_41 --> | EA | AP_42
    AP_42 --> | EA | AP_43[WP 4.3: Feldtest Campus<br/>D=7d]

    %% Projektabschluss
    AP_43 --> | EA | AP_13[WP 1.3: Projektabschluss<br/>D=10d]
    AP_13 --> M_End([Meilenstein: Projektabschluss])
```
# Konsistenz- und Plausibilitätsprüfung

## Prüfung der Abhängigkeiten

- WP 1.1 Projektplanung startet das Projekt.
- WP 2.1 Beschaffung Sensorik muss vor dem Hardwareaufbau erfolgen.
- WP 2.2 Aufbau Hardware muss vor der Anpassung der Sensorik erfolgen.
- WP 3.1 GUI Mockup kann parallel zur Hardwarebeschaffung beginnen.
- WP 3.2 Implementierung App und WP 3.3 Backend API bauen auf dem GUI-Konzept auf.
- WP 4.1 Funktionstest Hardware setzt fertige Hardware voraus.
- WP 4.2 Integrationstest benötigt Hardware, App und Backend.
- WP 4.3 Feldtest beginnt erst nach erfolgreichem Integrationstest.

## Kritischer Pfad

Vermutlich kritischer Pfad:

WP 1.1 (5d)
→ WP 3.1 (5d)
→ WP 3.3 (12d)
→ WP 4.2 (5d)
→ WP 4.3 (7d)

Gesamtdauer: 34 Tage

Dieser Pfad besitzt die längste Gesamtdauer und bestimmt den Projektendtermin.

## Plausibilitätsbewertung

Die Arbeitspakete besitzen logische Reihenfolgen. Hardware- und Softwareentwicklung laufen teilweise parallel. Die Integration erfolgt erst nach Fertigstellung aller wesentlichen Komponenten. Der Projektablauf erscheint realistisch und konsistent.

# Smart Waste - Projektablaufplan (Netzplan)


