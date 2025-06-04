# 🧱 Minecraft Server Manager – Node-RED Dashboard

Ein leistungsstarkes Node-RED-Dashboard zur Verwaltung deines Minecraft-Servers in Echtzeit. Es bietet Funktionen wie Spielerverwaltung, Sofort-Kits, visuelle Inventaranalyse und serverweite RCON-Kommandos – alles über eine intuitive Web-Oberfläche.

---

## 🚀 Funktionen im Überblick

### 🎮 Spielerverwaltung
- Automatische Auflistung aller online Spieler (alle 10 Sekunden aktualisiert)
- Dropdown-Auswahl speichert den gewählten Spieler für weitere Aktionen


### 🛡️ Rüstungs-Kits (mit Auto-Ausrüstung)
Verfügbare Kits:
- **Diamant-Rüstung**
- **Leder-Rüstung**
- **Kettenrüstung**
- **Gold-Rüstung**
- **Bogen-Kit** (Bogen, 360 Pfeile, Stärke-Effekt)
- **PVP-Kit** (Goldapfel, Eisenschwert, Netherite-Stiefel)

**Besonderheiten:**
- Automatische Ausrüstung direkt nach Vergabe
- Verzögerungen zwischen Kommandos zur Vermeidung von Flooding
- Visuelles Feedback im Debug-Panel

### 💡 Inventar-Visualisierung (LED-Anzeige)
- Analyse der Hotbar (Slots 0–8)
- Jeder Slot wird farblich einer LED zugeordnet
- Farbdatenbank für Items zur realitätsnahen Darstellung
- Warnsystem bei unbekannten Items

---

## ⚙️ Installation & Setup

### Voraussetzungen
- [Node-RED](https://nodered.org/) Instanz
- Minecraft-Server mit aktiviertem **RCON**
- Installierte Node-RED-Pakete:
  - `node-red-dashboard`
  - `node-red-contrib-rcon`

### Einrichtung
1. Importiere den Flow in deine Node-RED-Instanz
2. Konfiguriere die RCON-Verbindung:
   - IP-Adresse im `serverconfig`-Node setzen
   - RCON-Port anpassen (Standard: `25575`)
   - RCON-Passwort eintragen
3. *(Optional)* MQTT für LED-Anzeige konfigurieren:
   - MQTT-Broker im `mqtt-broker`-Node einrichten
   - Passenden Topic für dein LED-Setup wählen

---

## 🧑‍💻 Nutzung

### Spieler auswählen
- Online-Spieler werden automatisch aufgelistet
- Auswahl eines Spielers im Dropdown-Menü
- Alle Befehle wirken sich auf den gewählten Spieler aus

### Kits ausrüsten
- Klick auf einen Kit-Button vergibt automatisch alle Gegenstände
- Rüstung wird direkt angelegt
- Fortschritt und Status erscheinen im Debug-Fenster

### Inventar prüfen
- Klick auf **„Inventar Check“**:
  - Spielerinventar wird analysiert
  - Hotbar-Slots werden LEDs zugewiesen
  - Farben werden per MQTT (falls aktiviert) veröffentlicht

---

## 🧠 Technische Details

### Flow-Struktur

- **Spielerverwaltung:**
  - Periodisches Abrufen & Speicherung des Spielers
  - Inventar-Abfragen via RCON

- **Kit-System:**
  - Button-Trigger → Spielerprüfung → Item-Vergabe via RCON
  - 300ms Delay zwischen Kommandos
  - Auto-Ausrüstung per `/item replace` Befehl

- **LED-Visualisierung:**
  - Farbdatenbank zur Slot-Erkennung
  - MQTT-Ausgabe zur Ansteuerung externer Hardware

---

## 🛠️ Anpassung & Erweiterung

- **Kommando-Verzögerung anpassen:** Timeout-Werte in den Funktions-Nodes ändern
- **Neue Kits erstellen:** Bestehende Kit-Flows duplizieren und Items anpassen
- **LED-Farben ändern:** `itemColors`-Objekt im „Hotbar-Analyse“-Node bearbeiten

---



## 📄 Lizenz

Dieses Projekt ist Open Source und steht unter der [MIT License](https://opensource.org/licenses/MIT).












