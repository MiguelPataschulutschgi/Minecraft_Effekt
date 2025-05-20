# Minecraft Spieler-Effektanzeige mit MQTT und Node-RED

[GitHub Repository](https://github.com/dein-benutzername/dein-projekt)

## Was ist dieses Projekt?

Dieses Projekt ist ein Node-RED basiertes Dashboard-System zur Anzeige von Minecraft-Spieler-Effekten. Es verbindet sich per RCON mit einem Minecraft-Server, ruft die Effekte aktiver Spieler ab und visualisiert diese über MQTT-LED-Steuerung und ein UI-Dashboard. Spieler können im Dashboard ausgewählt werden, um deren aktuelle Effekte farblich angezeigt zu bekommen.

## Wie wird dieses Projekt installiert?

1. Node-RED installieren (https://nodered.org/docs/getting-started/)
2. Das Repository klonen oder die Flow-JSON in Node-RED importieren
3. Die Konfiguration des Minecraft-Servers im `serverconfig`-Node anpassen (Host, Port, Passwort)
4. MQTT-Broker konfigurieren (Adresse, Port, ggf. Authentifizierung)
5. Node-RED starten und auf das Dashboard zugreifen

## Wie funktioniert es?

- Der Flow ruft alle 10 Sekunden die Spielerliste vom Minecraft-Server ab und aktualisiert das Auswahlmenü im Dashboard.
- Ein Spieler kann aus dem Dropdown ausgewählt und die Auswahl per Button bestätigt werden.
- Ein Timer fragt alle 5 Sekunden die aktiven Effekte des ausgewählten Spielers ab.
- Die Effekte werden als farbige RGB-Werte umgerechnet und via MQTT an eine LED-Steuerung gesendet.
- Das Dashboard zeigt zusätzlich eine textuelle Übersicht des Spielerstatus und Effekts.
- Die Effekte werden visuell über Farben wie Feuer (Rot), Gift (Grün), Eis (Blau) etc. dargestellt.

## Welche Hardware wird benutzt?

- Ein Rechner oder Server mit Node-RED (z.B. Raspberry Pi, PC)
- MQTT-Broker (z.B. Mosquitto)
- LED-Controller oder Mikrocontroller (z.B. ESP32, Arduino) mit angeschlossenen RGB-LEDs zur Darstellung der Effekte
- Minecraft-Server mit aktivierter RCON-Schnittstelle

---

### Hinweis

Die RCON-Zugangsdaten und MQTT-Broker-Adresse müssen in den Nodes an dein Setup angepasst werden.  
Das Dashboard ist für einfache Bedienung und Visualisierung der Spieler-Effekte im Minecraft-Server gedacht.

---

Viel Spaß beim Verwenden und Anpassen!

