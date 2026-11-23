# Agiles Projektmanagement (Scrum) – Smart Waste App (Team 08)

## 1. Product Backlog (10 User Stories – MVP)

Das folgende priorisierte Product Backlog beschreibt die Kernfunktionen der **Smart Waste Mobile App (P2)** zur Überwachung und Steuerung der intelligenten Campus-Mülleimer (P1). Alle Stories sind nach den **INVEST-Kriterien** (*Independent, Negotiable, Valuable, Estimable, Small, Testable*) formuliert:

| Story-ID | User Story | Rolle | Ziel / Wunsch / Funktionalität | Nutzen |
| :--- | :--- | :--- | :--- | :--- |
| **US_01** | Als Reinigungskraft möchte ich eine Live-Übersicht der Füllstände aller Campus-Mülleimer sehen, um sofort zu erkennen, welche Behälter geleert werden müssen. | Reinigungskraft | Live-Übersicht der Füllstände (in %) aller Mülleimer | Vermeidung unnötiger Kontrollgänge und rechtzeitige Leerung |
| **US_02** | Als Reinigungskraft möchte ich eine interaktive Campus-Karte mit farblich markierten Mülleimer-Standorten sehen, um die Behälter schnell auf dem Gelände zu finden. | Reinigungskraft | Interaktive Campus-Karte mit GPS-Pins und Ampelfarben (Grün/Gelb/Rot) | Schnelle Orientierung auf dem Campus |
| **US_03** | Als Reinigungskraft möchte ich eine automatische Push-Benachrichtigung erhalten, sobald ein Mülleimer über 85 % gefüllt ist, um Überfüllungen auf dem Campus zu verhindern. | Reinigungskraft | Automatische Push-Benachrichtigung bei Überschreiten des Schwellenwerts | Sofortige Reaktion bei kritischen Füllständen |
| **US_04** | Als Reinigungskraft möchte ich eine optimierte Abholroute für alle aktuell vollen Mülleimer berechnen lassen, um meine Laufwege und Arbeitszeit zu minimieren. | Reinigungskraft | Berechnung der kürzesten Abholroute zwischen kritischen Mülleimern | Zeit- und Wegeersparnis bei der Entleerung |
| **US_05** | Als Facility Manager möchte ich die Warnschwellen (z. B. 80 % oder 90 %) pro Mülleimer-Typ individuell konfigurieren können, um auf unterschiedliche Abfallarten flexibel zu reagieren. | Facility Manager | Einstellungsmenü zur Anpassung der Füllstands-Schwellenwerte | Bedarfsgerechte Steuerung je nach Standort und Müllart |
| **US_06** | Als Facility Manager möchte ich den Batterie- und Solar-Ladestatus aller Sensoren einsehen können, um Ausfälle der Hardware frühzeitig zu erkennen. | Facility Manager | Anzeige von Akkustand (in %) und Solar-Ladezustand je Sensor | Proaktive Wartung und Vermeidung von Sensorausfällen |
| **US_07** | Als Techniker möchte ich einen einzelnen Sensor über die App neu kalibrieren oder neu starten können, um Messfehler nach einer Reinigung ohne Vor-Ort-Einsatz zu beheben. | Techniker | Remote-Befehl (Kalibrierung / Neustart) an den ESP32-Sensor senden | Reduzierung von Wartungseinsätzen vor Ort |
| **US_08** | Als Facility Manager möchte ich ein Statistik-Dashboard mit wöchentlichen und monatlichen Füllstands-Trends sehen, um langfristige Engpässe bei Mülleimer-Kapazitäten zu erkennen. | Facility Manager | Historische Auswertung und Diagramme der Entleerungszyklen | Datenbasierte Planung zusätzlicher Mülleimer |
| **US_09** | Als Campus-Nutzer (Studierender) möchte ich den nächstgelegenen freien Mülleimer nach Mülltrennung (Restmüll, Papier, Plastik) suchen können, um meinen Abfall korrekt zu entsorgen. | Campus-Nutzer | Filterbare Umkreissuche nach Abfallart und freier Kapazität | Förderung der Mülltrennung und sauberes Campus-Gelände |
| **US_10** | Als Systemadministrator möchte ich Benutzerrollen (Reinigungskraft, Techniker, Manager) und Zugriffsrechte verwalten können, um Konfigurationsfunktionen vor unbefugtem Zugriff zu schützen. | Systemadministrator | Login-System und rollenbasierte Rechteverwaltung (RBAC) | Sicherstellung der Datensicherheit und Systemintegrität |

---

## 2. Akzeptanzkriterien (für 4 ausgewählte User Stories)

### US_01: Live-Füllstandsanzeige
* **AK 1.1:** Alle registrierten Campus-Mülleimer werden in einer sortierbaren Listenansicht mit ID, Standortbezeichnung und aktuellem Füllstand in Prozent (0–100 %) angezeigt.
* **AK 1.2:** Die angezeigten Füllstandswerte aktualisieren sich automatisch mindestens alle 60 Sekunden oder manuell per „Pull-to-Refresh“ in unter 2 Sekunden.
* **AK 1.3:** Bei einem Verbindungsabbruch eines Sensors wird der letzte bekannte Wert mit einem deutlichen Zeitstempel und dem Status *„Offline“* markiert.
* **AK 1.4:** Mülleimer mit einem Füllstand $\ge 85\,\%$ werden automatisch ganz oben in der Liste hervorgehoben.

### US_02: Interaktive Campus-Karte
* **AK 2.1:** Die Karte zeigt den gesamten HFU-Campus mit korrekten GPS-Positionen (Abweichung $< 3\text{ Meter}$) aller installierten Smart-Waste-Behälter.
* **AK 2.2:** Jeder Mülleimer-Pin ist entsprechend seinem Füllstand farblich kodiert: Grün ($< 60\,\%$), Gelb ($60\text{–}84\,\%$) und Rot ($\ge 85\,\%$).
* **AK 2.3:** Beim Antippen eines Pins öffnet sich ein Info-Fenster mit Standortname, Müllart, exaktem Prozentwert und letzter Aktualisierungszeit.
* **AK 2.4:** Die Karte lässt sich flüssig zoomen und verschieben und zeigt bei aktiviertem GPS den eigenen aktuellen Standort des Nutzers an.

### US_03: Push-Benachrichtigungen bei kritischem Füllstand
* **AK 3.1:** Sobald ein Mülleimer den hinterlegten Schwellenwert (Standard: $85\,\%$) überschreitet, wird innerhalb von maximal 30 Sekunden eine Push-Benachrichtigung an eingeloggte Reinigungskräfte gesendet.
* **AK 3.2:** Die Benachrichtigung enthält eindeutig die Mülleimer-ID, den Standort und den aktuellen Füllstand in Prozent.
* **AK 3.3:** Ein Tippen auf die Push-Benachrichtigung öffnet direkt die Detailansicht bzw. Kartenposition des betroffenen Mülleimers in der App.
* **AK 3.4:** Pro Mülleimer wird maximal eine Warnmeldung pro Überfüllungszyklus versendet (kein Spam bei schwankenden Messwerten), bis der Behälter wieder unter $20\,\%$ geleert wurde.

### US_04: Optimierte Abholroute
* **AK 4.1:** Per Klick auf *„Route starten“* berechnet die App eine Wegstrecke, die alle Mülleimer mit einem Füllstand $\ge 85\,\%$ miteinander verbindet.
* **AK 4.2:** Die berechnete Route wird als durchgehende Linie auf der Campus-Karte dargestellt und zeigt die geschätzte Gehzeit in Minuten sowie die Gesamtdistanz in Metern an.
* **AK 4.3:** Sobald ein Mülleimer auf der Route geleert wurde (Füllstand fällt unter $15\,\%$), wird er automatisch als *„Erledigt“* abgehakt und die Restroute aktualisiert.
* **AK 4.4:** Falls aktuell kein Mülleimer über $85\,\%$ gefüllt ist, zeigt die App die Meldung *„Aktuell keine kritischen Mülleimer vorhanden“* an.

---

## 3. Estimation Meeting (Planning Poker)

Im Estimation Meeting wurde zunächst **US_05 (Warnschwellen konfigurieren)** als kleine, klar abgegrenzte und gut verständliche **Referenz-Story mit 3 Story Points (SP)** festgelegt. Alle weiteren neun User Stories wurden relativ dazu auf der modifizierten Fibonacci-Skala (`0, 0.5, 1, 2, 3, 5, 8, 13, 21, 40, 100`) geschätzt:

| Story-ID | Kurzbeschreibung | Story Points (SP) | Priorität | Begründung der Einstufung (relativ zu US_05 = 3 SP) |
| :--- | :--- | :--- | :--- | :--- |
| **US_05** | Warnschwellen konfigurieren *(Referenz)* | **3 SP** | Mittel | **Referenz-Story:** Einfaches Einstellungsformular mit Datenbank-Update, geringer technischer Komplexität |
| **US_06** | Batterie- und Solar-Ladestatus anzeigen | **2 SP** | Mittel | Kleiner als die Referenz-Story, da reine Lese-Anzeige eines bereits übertragenen Sensorwerts |
| **US_01** | Live-Füllstandsanzeige aller Mülleimer | **5 SP** | Sehr hoch | Etwas aufwendiger als US_05 durch Echtzeit-Polling/Auto-Refresh, Sortierlogik und Offline-Erkennung |
| **US_03** | Push-Benachrichtigungen bei Überfüllung | **5 SP** | Sehr hoch | Benötigt serverseitige Schwellenwert-Prüfung, Push-Service-Anbindung (FCM) und Anti-Spam-Sperre |
| **US_07** | Sensor-Neustart / Kalibrierung (Remote) | **5 SP** | Niedrig | Bidirektionale Kommunikation (App $\rightarrow$ Backend $\rightarrow$ ESP32) erfordert sichere Befehlsbestätigung |
| **US_08** | Statistik-Dashboard (Trends) | **5 SP** | Niedrig | Historische Datenaggregation und Darstellung von Verlaufsdiagrammen (höherer UI-Aufwand) |
| **US_02** | Interaktive Campus-Karte mit Pins | **8 SP** | Sehr hoch | Deutlich komplexer durch Karten-SDK-Integration, GPS-Positionierung und dynamische Pin-Färbung |
| **US_09** | Umkreissuche für Campus-Nutzer | **8 SP** | Niedrig | Kombiniert Kartenansicht, Standortbestimmung und mehrstufige Filterung nach Abfallart/Kapazität |
| **US_10** | Benutzerrollen & Rechteverwaltung (RBAC) | **8 SP** | Hoch | Sicherheitskritische Authentifizierung, Session-Handling und Rechtematrix über alle Ansichten |
| **US_04** | Optimierte Abholroute berechnen | **13 SP** | Hoch | Höchste Komplexität durch Routing-Algorithmus (Shortest Path), Live-Neuberechnung und Karten-Overlay |
| **Gesamt** | **Alle 10 User Stories (MVP)** | **62 SP** | | |

---

## 4. Sprint Planning (Sprint 1)

**Rahmenbedingungen für Sprint 1:**
* **Team-Setup:** 3 Developer, Sprint-Dauer: 2 Wochen
* **Team-Velocity / Kapazität:** maximal **20 Story Points**
* **Sprint-Ziel (Sprint Goal):** *„Bereitstellung der Kernfunktionen für Reinigungskräfte (Live-Füllstände, Campus-Karte, Push-Warnungen und Schwellenwert-Konfiguration), damit kritische Mülleimer in Echtzeit erkannt und lokalisiert werden können.“*

### Sprint 1 Backlog (Ausgewählte User Stories)

| Story-ID | User Story (Kurzform) | Story Points (SP) | Priorität | Auswahlbegründung für Sprint 1 |
| :--- | :--- | :--- | :--- | :--- |
| **US_01** | Live-Füllstandsanzeige | **5 SP** | Sehr hoch | Fundament der gesamten App; liefert den direkten Hauptnutzen für Reinigungskräfte |
| **US_02** | Interaktive Campus-Karte | **8 SP** | Sehr hoch | Ermöglicht sofortige visuelle Lokalisierung der Mülleimer; Basis für spätere Routenplanung (US_04) |
| **US_03** | Push-Benachrichtigungen | **5 SP** | Sehr hoch | Sichert proaktive Alarmierung bei $> 85\,\%$ Füllstand und schließt den Kern-Workflow ab |
| **US_06** | Batterie- & Solar-Ladestatus | **2 SP** | Mittel | Nutzt dieselbe Sensor-Datenschnittstelle wie US_01 und füllt die Restkapazität exakt auf 20 SP auf |
| **Summe Sprint 1** | **4 User Stories** | **20 SP** | | **Kapazitätsgrenze (20 SP) optimal ausgeschöpft (100 % Auslastung)** |

**Zusammenfassende Begründung:**
Die ausgewählten Stories decken den höchsten Geschäftswert (*Business Value*) für die Hauptzielgruppe (Reinigungskräfte) ab und bilden bereits nach 2 Wochen ein einsatzfähiges Produktinkrement. Zudem schafft **US_02** (Campus-Karte) die technische Grundlage für die darauf aufbauende Routenberechnung (**US_04**) in Sprint 2.

---

## 5. Releaseplanung (Folge-Sprints)

Die verbleibenden **6 User Stories (42 SP)** werden unter strikter Einhaltung der Obergrenze von **maximal 20 Story Points pro Sprint** auf drei weitere Zwei-Wochen-Sprints verteilt:

| Sprint | Zeitraum (Richtwert) | Zugewiesene User Stories | Story Points je Story | Summe SP (max. 20 SP) | Fokus / Release-Inkrement |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Sprint 1** | Woche 1 – 2 | **US_01, US_02, US_03, US_06** | 5 + 8 + 5 + 2 | **20 SP** | **Kern-MVP (Monitoring & Alarmierung):** Live-Daten, Karte, Push-Warnungen, Akkustatus |
| **Sprint 2** | Woche 3 – 4 | **US_04, US_05** | 13 + 3 | **16 SP** | **Operative Optimierung:** Optimierte Abholroute (baut auf US_02 auf) & konfigurierbare Warnschwellen |
| **Sprint 3** | Woche 5 – 6 | **US_10, US_07** | 8 + 5 | **13 SP** | **Sicherheit & Fernwartung:** Rollen-/Rechteverwaltung (RBAC) & Remote-Sensor-Neustart |
| **Sprint 4** | Woche 7 – 8 | **US_08, US_09** | 5 + 8 | **13 SP** | **Erweiterte Funktionen (Full Release):** Statistik-Dashboard & öffentliche Umkreissuche für Studierende |
| **Gesamt** | **8 Wochen (4 Sprints)** | **10 User Stories** | | **62 SP** | **Vollständiges Produkt-Release (P2)** |