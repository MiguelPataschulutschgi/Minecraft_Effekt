# 🎮 Minecraft Status Effects Monitor mit LED-Visualisierung

Dieses Projekt zeigt die **aktiven Status-Effekte von Minecraft-Spielern in Echtzeit** über ein **Node-RED Dashboard** an. Die Effekte werden per RCON vom Minecraft-Server abgefragt und als **RGB-Farben über MQTT** an z. B. LED-Streifen weitergegeben.

---

![Screenshot des Dashboards](./screenshot.png) <!-- Füge hier dein Bild ein -->

## 🧰 Funktionen

- 🔄 Automatische Spieler-Abfrage per RCON
- 🧍 Auswahl von Spielern und Entities über das Dashboard
- 💡 Live-Visualisierung von Effekten auf RGB-LEDs (z. B. WS2812b)
- 📶 MQTT-Integration zur Steuerung externer Hardware
- 💊 Darstellung von Effekten, Leben & Entities im UI
- 🎲 Zufalls-Herzvergabe über Button
- 🧠 Einfache Erweiterbarkeit

---

## 📦 Voraussetzungen

### Software

- [Node-RED](https://nodered.org/)
- Minecraft Java Server mit aktivierter **RCON**
- MQTT-Broker (z. B. [Mosquitto](https://mosquitto.org/), CloudMQTT, tome.lu)

### Node-RED Module

Installiere diese über „Manage Palette > Install“:

- `node-red-dashboard`
- [`@tomsith/node-red-contrib-minecraft`](https://www.npmjs.com/package/@tomsith/node-red-contrib-minecraft) – Version **0.7.7**
- `node-red-contrib-mqtt`
- `node-red-contrib-ui-led` *(optional)*

---

## 🔧 Installation & Einrichtung

### 1. Node-RED installieren

```bash
npm install -g --unsafe-perm node-red
2. Node-RED starten
bash
Kopieren
Bearbeiten
node-red
3. Dashboard & Flow
Öffne Node-RED unter: http://localhost:1880

Importiere den Flow: Menu → Import → Flow-JSON einfügen

Öffne das Dashboard: http://localhost:1880/ui

4. Konfiguration
Passe folgende Nodes im Flow an:

rcon-Node: IP, Port, Passwort deines Minecraft-Servers

mqtt-broker: Adresse deines Brokers (z. B. mqtt://localhost)

LED-Ziel-Topic: z. B. led/rgb

🧠 Funktionsweise
Spielerliste abrufen
Automatisch alle 10 Sekunden

Dropdown zur Spielerwahl im Dashboard

Effekte überwachen
Effekte werden alle 5 Sekunden abgefragt

Der erste erkannte Effekt bestimmt die RGB-Farbe

MQTT-Ausgabe
RGB-Wert wird an MQTT-Topic z. B. led/rgb gesendet

LED-Controller (ESP32, Tasmota etc.) zeigt die entsprechende Farbe

Entity-Modus
Das Dashboard erlaubt das Spawnen von Mobs mit Effekten

Zufallsmodus
Button im Dashboard setzt zufällige Herzanzahl auf einen Spieler

🎨 Effektfarben (Beispiel)
Effekt	RGB-Farbe
Feuer	255, 69, 0
Gift	0, 255, 0
Eis	173, 216, 230
Blutung	139, 0, 0
Regeneration	64, 224, 208
Stärke	0, 0, 255

🔧 Die Farben kannst du im Function-Node selbst anpassen!

🛠️ Hardware-Beispiel
Komponente	Beispiel
LED-Controller	ESP32 mit MQTT-Firmware (ESPHome, Tasmota)
LED-Streifen	WS2812b oder kompatible
MQTT-Broker	Mosquitto lokal oder extern
Steuerung	Raspberry Pi, PC oder Docker-Container








