# IoT-Based Home Automation System using Arduino Uno & PICSimLab

This repository contains an **IoT-based home automation and monitoring system** built around an **Arduino Uno** and simulated in **PICSimLab**.  

The project combines:

- Temperature monitoring & control  
- Water-level monitoring using a virtual tank  
- Remote control of heater, cooler, inlet, and outlet valves from a mobile app / IoT dashboard

All the hardware is simulated, so you can test the full project without any physical components.

---

## ✨ Features

- 📡 **Real-time monitoring**
  - Temperature (°C)
  - Water level / tank volume

- 🧊🔥 **Actuator control**
  - Heater ON/OFF  
  - Cooler/Fan ON/OFF  
  - Tank inlet valve ON/OFF  
  - Tank outlet valve ON/OFF  

- 📱 **IoT mobile dashboard**
  - Displays temperature and tank level
  - Buttons to toggle heater, cooler, inlet, outlet
  - Updates status in sync with the simulation

- 💻 **PICSimLab virtual hardware**
  - LCD 16x2 (via PCF8574 I²C backpack)
  - LDR module
  - Fan/heater block
  - W5500 / serial interface for PC app
  - Serial Remote Tank simulator for water level

---

## 🏗 System Architecture

1. **Arduino Uno (in PICSimLab)**  
   - Reads temperature and tank level (via Serial Remote Tank).  
   - Controls heater, cooler, inlet, and outlet pins.  
   - Updates LCD with:
     - `T=xx.xx` (temperature)  
     - `V=xxxx` (tank volume)  
     - Inlet status (e.g. `IN_FL_ON` / `IN_FL_OFF`).

2. **PC / Serial Application**
   - PICSimLab’s *Serial Remote Tank* simulates tank physics (inlet/outlet flow, capacity, etc.).
   - Communicates with Arduino over serial (COM port).

3. **Mobile App / IoT Platform**
   - Connects to PC/Arduino through Wi-Fi / internet (e.g., via MQTT, HTTP, or another bridge).
   - Sends commands to control actuators and receives sensor values.

---

## 🧰 Requirements

### Software

- [PICSimLab](https://sourceforge.net/projects/picsim/)  
- Arduino IDE (for compiling the `.ino` sketch)  
- Serial terminal / bridge (built into PICSimLab or external)  
- Mobile IoT app / dashboard (e.g., custom Android app, Blynk, etc.)

### Simulated Hardware in PICSimLab

- Arduino Uno board
- 16x2 LCD with PCF8574 I²C backpack
- LDR sensor module (optional visual feedback)
- Fan / heater block
- W5500 / Serial interface (or standard UART)
- Serial Remote Tank module

---

