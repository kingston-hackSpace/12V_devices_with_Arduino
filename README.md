# Controlling 5-12V devices with Arduino

This guide explains how to safely control **5–12V devices** such as motors, fans, pumps, and LED strips using an Arduino board.

This tutorial uses an **IRLZ44N logic-level MOSFET**, which is the ideal component for this application.  An **old-school alternative** is using a **TIP120 transistor** instead of a MOSFET but is less efficient. See the TIP120 tutorial [here]-pending


-----
### Why it matters

- USING 12V DEVICES 

Arduino pins can provide up to 5V signals, which is not enough to ***power*** a 12V device. However, you can still use Arduino to ***control*** a 12V device by using additional electronic components and a 12V power supply. More info below. 

*NOTE: Arduino **VIN pin** stands for "Voltage-IN", supporting up to 12V. However, this is not an output pin, it works only as an input alternative board powering pin.* 

- ⚠️ USING 5V / HIGH CURRENT DEVICES 

Although Arduino pins provide 5V signals, they can only supply about **~20 mA**. Many 5V devices require much more current (such as motors and LED strips). Connecting them directly to an Arduino pin can overheat the board or wiring and create serious electrical hazards. Always use an external power supply and proper switching components for high‑current loads.

---
## ⚠️ IMPORTANT! WIRE TYPE! 

If your devices draws high current, you will need thicker wires. **Talk with a technician for more guidance.**

See reference below:

- Up to 500mA → 0.1 mm² (jumper wires for small electronics) (28 AWG)

- Up to ~3 A → 0.5 mm² (20-22 AWG) (thin wires available at hackSpace)

- Up to ~5 A → 0.75 mm² (18 AWG)

- 5–10 A → 1.5 mm² (15–16 AWG)

Read more [about wires](https://github.com/kingston-hackSpace/About_wires) here. 

---
## HARDWARE

Develop your project using the following equipment:

- Power Supply

- Arduino board

- IRLZ44N MOSFET (used to switch high current/voltage from the power supply using a control signal from the Arduino)

- Diode 1N4007 or 1N4001 (protects the circuit from voltage spikes)

- 220ohms resistor (protects the Arduino signal pin)

- 1K resistor (grounds MOSFET's Gate to reduce electrical noise)

---
## DIAGRAM

⚠️ IMPORTANT NOTE! MOSFET pins are not interchangeable. Follow [this MOSFET diagram BEFORE WIRING](https://github.com/kingston-hackSpace/12V_devices_with_Arduino/blob/main/IRLZ44N.png)

See [diagram here]

---
## ABOUT THE IRLZ44N MOSFET

The IRLZ44N MOSFET is the main component that allows us to control a 12 V actuator using a 5 V signal from an Arduino.

The IRLZ44N can be used:

- As an on/off switch

- With PWM signals, for example to control motor speed or LED brightness

⚠️ At 5 A the IRLZ44N will get warm. For higher currents (up to 10 A), you must use a heatsink and allow air flow.




