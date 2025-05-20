# Minecraft Spieler-Effektanzeige mit Node-RED & MQTT

[GitHub Repository](https://github.com/dein-benutzername/dein-projekt)

## 🧩 Was ist dieses Projekt?

Dieses Projekt zeigt die aktiven **Status-Effekte von Minecraft-Spielern** in Echtzeit über ein Dashboard an. Die Daten werden per RCON vom Minecraft-Server abgefragt und über MQTT farblich auf RGB-LEDs visualisiert. Ideal für Visualisierung in Echtzeit auf Displays oder LED-Leisten.

## 🛠️ Installation

1. Installiere [Node-RED](https://nodered.org/docs/getting-started/)
2. Importiere den bereitgestellten Flow in Node-RED
3. Passe die folgenden Dinge in den Nodes an:
   - **Minecraft-Serverkonfiguration** (`serverconfig` Node): Host, Port, Passwort
   - **MQTT-Broker** (z. B. `tome.lu`): Adresse und Port
4. Stelle sicher, dass dein Minecraft-Server RCON aktiviert hat
5. Öffne das Node-RED Dashboard im Browser (Standard: `http://localhost:1880/ui`)

## ⚙️ Wie funktioniert es?

- Alle 10 Sekunden wird die Spielerliste vom Server abgerufen.
- Du kannst im Dashboard einen Spieler aus einem Dropdown auswählen.
- Ein Button startet die Überwachung des Effekts dieses Spielers.
- Alle 5 Sekunden werden die Effekte dieses Spielers abgefragt.
- Die Effekte (z. B. Feuer, Gift, Eis, Blutung, Regeneration) werden über Farben in RGB umgerechnet.
- Diese Farben werden über MQTT z. B. an ein LED-Device gesendet.
- Zusätzlich wird der Effekttext im Dashboard angezeigt.

## 💡 Beispielhafte Effekte & Farben

| Effekt        | Farbe (LED) |
|---------------|-------------|
| Feuer         | Rot-Orange  |
| Gift          | Grün        |
| Eis           | Hellblau    |
| Blutung       | Dunkelrot   |
| Regeneration  | Türkis      |

## 🧱 Verwendete Hardware

- Node-RED-fähiges Gerät (z. B. Raspberry Pi, PC)
- MQTT-Broker (lokal oder online, z. B. Mosquitto)
- RGB-LEDs mit MQTT-fähiger Steuerung (z. B. ESP32 oder Arduino mit LED-Streifen)
- Minecraft-Server mit RCON-Zugang

## 🖥️ Dashboard

- **Dropdown-Menü** zur Spielerauswahl
- **Button**, um Effekte zu laden
- **Textanzeige** mit dem aktuellen Effektstatus
- **Farbvisualisierung** per MQTT auf LED-Ausgabe

---

**Hinweis:** Es werden keine Rüstungen oder Items vergeben – der Fokus liegt ausschließlich auf dem **Live-Monitoring der aktiven Effekte von Spielern**.

---

Viel Spaß beim Experimentieren!  
👉 Stelle sicher, dass RCON korrekt konfiguriert ist und der MQTT-Ausgang mit deinem LED-System funktioniert.
