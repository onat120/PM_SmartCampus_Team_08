```mermaid
graph LR

Start([Start])

WP11[WP 1.1 Projektplanung<br/>5d]
WP21[WP 2.1 Beschaffung Sensorik<br/>3d]
WP22[WP 2.2 Aufbau Hardware<br/>6d]
WP23[WP 2.3 Anpassung Sensorik<br/>7d]

WP31[WP 3.1 GUI Mockup<br/>5d]
WP32[WP 3.2 Implementierung App<br/>8d]
WP33[WP 3.3 Backend API<br/>12d]

WP41[WP 4.1 Funktionstest Hardware<br/>4d]
WP42[WP 4.2 Integrationstest System<br/>5d]
WP43[WP 4.3 Feldtest Campus<br/>7d]

Ende([Projektende])

Start --> WP11

WP11 -->|EA| WP21
WP21 -->|EA + 7d Lead Time| WP22
WP22 -->|EA| WP23

WP11 -->|AA| WP31
WP31 -->|EA| WP32
WP31 -->|AA| WP33

WP23 -->|EA| WP41

WP32 -->|EA| WP42
WP33 -->|EA| WP42
WP41 -->|EA| WP42

WP42 -->|EA| WP43

WP43 --> Ende
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