# KI-Gestütztes Ablaufnetz-Audit

## Verwendeter Prompt
> "Analysiere den folgenden Mermaid-Netzplan auf logische Fehler, Zirkelbezüge, Brooks's Law (Parallellauf/Ressourcen) und Lieferketten-Risiken. Gib konkrete Korrekturvorschläge:"

## Kernaussagen & Warnungen der KI
* **Kritischer Fehler (Zirkelbezug):** Der Rückkopplungspfeil von `AP 2.03` auf `AP 2.01` blockiert die Ausführung des gesamten Software-Strangs.
* **Logikfehler im Hardware-Pfad:** Der Feldtest (`AP 3.02`) findet vor der eigentlichen Hardware-Montage (`AP 1.03`) statt.
* **Lieferketten-Engpass:** Die 14-tägige Lead Time der LoRaWAN-Sensorik liegt auf dem kritischen Pfad und verzögert das Gesamtprojekt ohne zeitlichen Puffer.

## Konkrete Anpassungen
1. Entfernen der Zeile `AP_203 --> | EA | AP_201`.
2. Umhängen von `AP 1.03` (Montage): Muss direkt nach Ablauf der 14d Lead Time von `AP 1.02` erfolgen und VOR `AP 3.01` (Integration) geschaltet werden.