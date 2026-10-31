# Sample Schedule (Fehlerhafter Prüfplan)

```mermaid
graph TD
    M_Start([Start: Projektbeginn]) --> AP_101[AP 1.01: Sensor- & HW-Spezifikation<br/>D=2d]
    
    %% Hardware-Strang
    AP_101 --> | EA | AP_102[AP 1.02: LoRaWAN-Sensorik bestellen<br/>D=1d]
    AP_102 --> | EA + 14d Lead Time | AP_103[AP 1.03: Sensor-Gehäuse & Montage<br/>D=3d]
    
    %% Gateway / Infrastruktur
    AP_101 --> | EA | AP_104[AP 1.04: LoRaWAN-Gateway-Konfiguration<br/>D=2d]
    
    %% Software-Strang
    AP_101 --> | AA | AP_201[AP 2.01: Backend Data-Pipeline<br/>D=5d]
    AP_201 --> | EA | AP_202[AP 2.02: Datenbank-Schema & API-Design<br/>D=3d]
    AP_202 --> | EA | AP_203[AP 2.03: Dashboard-Frontend Entwicklung<br/>D=4d]
    AP_203 --> | EA | AP_201
    
    %% Integration & Test
    AP_102 --> | EA | AP_301[AP 3.01: System-Integration & E2E-Test<br/>D=4d]
    AP_203 --> | EA | AP_301
    AP_301 --> | EA | AP_302[AP 3.02: Feldtest & Campus-Rollout<br/>D=5d]
    AP_302 --> | EA | AP_103
    AP_302 --> M_End([Meilenstein: Projektabschluss])
```


---

#### 2. Manuelle Prüfung in `02_WBS_Planning/Schedule Audit (Manual).md` anlegen
Erstelle diese Notiz und füge folgende manuell identifizierte Fehler ein:
# Manuelles Audit des Beispiel-Ablaufplans

## Identifizierte Fehler und Anomalien

1. **Zirkelbezug / Logischer Kreis (Deadlock):**
   * Zwischen `AP 2.01`, `AP 2.02` und `AP 2.03` existiert eine geschlossene Schleife (`AP 2.03 --> | EA | AP_201`). Dadurch ist der Netzplan mathematisch unlösbar.

2. **Fehlende / Falsche Hardware-Abhängigkeiten:**
   * `AP 3.01` (System-Integration) hängt direkt an `AP 1.02` (Bestellung), obwohl die physische Hardware erst nach `AP 1.03` (Montage) bereitsteht.
   * `AP 1.03` (Montage) wird erst nach `AP 3.02` (Feldtest & Rollout) ausgeführt. Man kann keinen Feldtest durchführen, bevor das Gehäuse montiert ist.

3. **Versteckte Risiken & Brooks's Law:**
   * Es sind keine Kapazitäts-Puffer für die lange Lieferzeit (14 Tage Lead Time) eingeplant.