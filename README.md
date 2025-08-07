# SfES-Edrys-Lab

## Arduino Debugging Lab

Willkommen im **Arduino Debugging Lab** zur Fehlersuche in Mikrocontroller-Anwendungen.  
Ziel ist es, typische Programmierfehler in drei Arduino-Projekten zu analysieren, zu korrigieren und zu testen.

---

### Docker Setup (für Lehrkräfte)

```bash
docker run -it -p 5000:5000 --device=/dev/ttyACM0:/dev/ttyACM0 crosslab/edrys_pyxtermjs_arduino:latest
```

### Überblick

In diesem Lab arbeitest du mit **drei fehlerhaften Arduino-Programmen**.  
Deine Aufgabe ist es, die Fehler zu identifizieren, zu beheben und das Ergebnis über Livestream zu validieren.

#### Zeitvorgabe
- **15 Minuten pro Aufgabe**

#### Benötigte Hardware
- Arduino Uno  
- RGB-LED (an D9, D10, D11)  
- Servo-Motor (an D3)  
- IR-Sensor (an A3)

---

### Aufgabenbeschreibung

#### Aufgabe 1: RGB-LED Steuerung

**Ziel:** RGB-LED soll sauber zwischen Rot, Grün und Blau wechseln – ohne Farbmischungen.

**Fehlerbeschreibung:**
- Vorherige Farben werden nicht gelöscht.
- Es erfolgt nur eine OR-Verknüpfung beim Einschalten.

**Symptome:**
- Lila statt Rot, Gelb statt Grün, Weiß nach Blau.

**Lernziel:**
- Registerprogrammierung und bitweise Operationen verstehen.

---

#### Aufgabe 2: Watchdog-Timer

**Ziel:** Das Programm soll dauerhaft laufen und eine LED regelmäßig blinken lassen – ohne unerwartete Resets.

**Fehlerbeschreibung:**
- Der Watchdog-Timer wird nicht zurückgesetzt (`wdt_reset()` fehlt).

**Symptome:**
- Unerwartete Programmresets, unregelmäßiges Verhalten.

**Lernziel:**
- Bedeutung und korrekter Einsatz von Watchdog-Timern.

---

#### Aufgabe 3: ADC-Auswertung des IR-Sensors

**Ziel:** Der Servo soll auf Basis eines IR-Sensors entweder auf 0° oder 180° fahren und eine passende LED anzeigen.

**Fehlerbeschreibung:**
1. Falscher ADC-Kanal (A0 statt A3).
2. Ungeeigneter Datentyp (8 Bit statt 10 Bit).
3. Zu hoher Schwellwert (>1000).

**Symptome:**
- Keine oder falsche Reaktion auf Objekte vor dem Sensor.

**Lernziel:**
- Sensorik kalibrieren, ADC richtig konfigurieren.
