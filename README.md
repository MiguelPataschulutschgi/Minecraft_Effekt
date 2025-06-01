Minecraft Server Manager - Node-RED Dashboard
Overview
This Node-RED project provides a web-based dashboard for managing a Minecraft server with the following features:

Player selection and management

Instant armor kits with auto-equip functionality

Real-time inventory tracking with LED visualization

Server command execution via RCON

Key Features
Player Management
Dropdown menu automatically lists all online players

Selected player is stored for subsequent commands

Player inventory inspection system

Armor Kits
Available Kits:

Diamond Armor

Leather Armor

Chainmail Armor

Gold Armor

Bow Kit (includes bow + 360 arrows + strength effect)

PVP Kit (golden apple, iron sword, netherite boots)

Special Features:

Kits are immediately equipped on the player

Items are given with small delays to prevent command flooding

Visual feedback for each command execution

Inventory Visualization
Tracks items in player's hotbar (first 9 slots)

Each slot corresponds to an LED with color matching the item type

Comprehensive item color database for accurate representation

Automatic detection of unknown items with warning system

Installation
Prerequisites
Node-RED instance

Minecraft server with RCON enabled

node-red-dashboard and node-red-contrib-rcon packages installed

Setup
Import the flow into your Node-RED instance

Configure the RCON connection:

Update server IP in the serverconfig nodes

Set correct RCON port (default: 25575)

Enter your RCON password

(Optional) Configure MQTT if using LED visualization:

Set MQTT broker details in the mqtt-broker node

Ensure topic matches your LED controller

Usage
Player Selection
The system automatically polls for online players every 10 seconds

Select a player from the dropdown menu

All subsequent commands will apply to this player

Armor Kits
Click any armor kit button

The system will:

Give all pieces of the armor set

Automatically equip each piece

Provide visual feedback in the debug panel

Inventory Tracking
Click "Inventar Check" button

The system will:

Query the player's inventory

Analyze hotbar items

Map each slot to an LED color

Publish colors via MQTT (if configured)

Technical Details
Flow Structure
Player Management Section:

Periodic player list updates

Player selection storage

Inventory inspection commands

Kit Delivery System:

Button triggers → Player verification → Item generation → RCON execution

Built-in delays between commands (300ms)

Auto-equip functionality using /item replace commands

LED Visualization:

Comprehensive item color database

Slot mapping system

MQTT output for hardware integration

Customization
Change Command Delays: Modify the timeout values in the kit functions

Add New Kits: Duplicate existing kit flows and update item lists

Adjust LED Colors: Edit the itemColors object in the "Hotbar-Item Analyse" function

Troubleshooting
Common Issues
Commands not executing:

Verify RCON connection details

Check server logs for command errors

Ensure selected player is online

LEDs not updating:

Confirm MQTT broker connection

Check topic matches your controller

Verify item color definitions

Unknown items in inventory:

The system will log unknown items - add their colors to the itemColors object

Roadmap
Add more kit variations

Implement player teleportation features

Add server performance monitoring

Create mobile-responsive dashboard layout

License
This project is open-source and available under the MIT License.










