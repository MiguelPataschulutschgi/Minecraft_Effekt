# 🎮 Minecraft Status Effects Monitor mit LED-Visualisierung

Dieses Projekt zeigt die **aktiven Status-Effekte von Minecraft-Spielern in Echtzeit** über ein **Node-RED Dashboard** an. Die Effekte werden per RCON vom Minecraft-Server abgefragt und als **RGB-Farben über MQTT** an z. B. LED-Streifen weitergegeben.

---

![Screenshot des Dashboards](./screenshot.png) <!-- Du kannst hier deinen Screenshot einfügen -->

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
- `node-red-contrib-minecraft`
- `node-red-contrib-mqtt`
- `node-red-contrib-ui-led` *(optional)*

---

## 🔧 Installation & Einrichtung

### 1. Node-RED installieren

```bash
npm install -g --unsafe-perm node-red
.
