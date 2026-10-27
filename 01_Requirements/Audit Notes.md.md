# Requirements Audit Report - Smart Waste

## 1. Vage Adjektive (Qualitätsmängel)
- **REQ_07 (Live-Füllstandsanzeige):** Das Adjektiv *"übersichtlich"* in der Beschreibung ist vage und nicht testbar. **Korrekturhinweis:** Besser definieren als *"in einer tabellarischen Listenansicht sortiert nach prozentualem Füllstand"*.
- **REQ_04 (Wetterfestes Sensorgehäuse):** Das Wort *"störungsfrei"* im Akzeptanzkriterium ist nicht exakt messbar. **Korrekturhinweis:** Ändern zu *"der Mikrocontroller sendet nach dem Wassertest weiterhin im regulären Takt Datenpakete"*.

## 2. Widersprüche (Hardware vs. Software)
- **KRITISCHER WIDERSPRUCH:** Es besteht ein technischer Konflikt zwischen **REQ_02 (Autarke Solarstromversorgung)** und **REQ_07 (Live-Füllstandsanzeige) / REQ_03 (GPS)**. Eine permanente, drahtlose Echtzeit-Übertragung ("Live") sowie permanentes GPS-Tracking saugen den kleinen ESP32-Akku binnen Stunden leer. Dies widerspricht der geforderten Laufzeit von 7 Tagen ohne Netzstrom.
- **Lösungsempfehlung:** REQ_07 anpassen: Statt "Live-Füllstand" auf "periodische Füllstandsübermittlung (z. B. Deep-Sleep Wakeup alle 30 Minuten)" umstellen, um das Hardware-Constraint REQ_02 zu erfüllen.

## 3. Fehlende Nicht-Funktionale Anforderungen (NFA)
- **Security / Authentifizierung:** Es fehlt ein Rollenkonzept. Laut REQ_08 darf der "Administrator" Warnschwellen ändern. Es gibt jedoch keine NFA, die einen passwortgeschützten Login vorschreibt, um unbefugte Änderungen durch Dritte zu verhindern.
- **Latenz:** Bei den Push-Benachrichtigungen (REQ_10) ist keine maximale Latenzzeit definiert (z. B. *"MUSS innerhalb von 5 Sekunden zugestellt werden"*).
- **Ausfallsicherheit (Fallback):** Was passiert, wenn das WLAN ausfällt oder der Sensor blockiert ist? Es fehlt eine Constraint-Anforderung für lokales Offline-Caching der Messwerte auf dem ESP32, bis die Verbindung wiederhergestellt ist.