# Controlling 5-12V devices with Arduino

This guide explains how to safely control **5–12V devices** such as motors, fans, pumps, and LED strips using an Arduino board.

This tutorial uses an **IRLZ44N logic-level MOSFET**, which is the ideal component for this application.  An **old-school alternative** is using a **TIP120 transistor** instead of a MOSFET but is less efficient. See the TIP120 tutorial [here]-pending


-----
### Why it matters

- USING 12V DEVICES 

Arduino pins can provide up to 5V signals, which is not enough to power a 12V device. However, you can still use Arduino to control a 12V device by using additional electronic components and a 12V power supply. More info below. 

- ⚠️ USING 5V / HIGH CURRENT DEVICES 

Although Arduino pins provide 5V signals, they can only supply about **~20 mA**. Many 5V devices require much more current. Connecting them directly to an Arduino pin can overheat the board or wiring and create serious electrical hazards. Always use an external power supply and proper switching components for high‑current loads.

*NOTE: Arduino **VIN pin** stands for "Voltage-IN", supporting up to 12V. However, this is not an output pin, it works only as an input alteranative board powering pin.* 

--
## ⚠️ IMPORTANT! WIRE TYPE! 

If your devices draws high current, you will need thicker wires. **Talk with a technician.**

See reference guide below:

- Up to 500mA → 0.1 mm² (jumper wires for small electronics) (28 AWG)

- Up to ~3 A → 0.5 mm² (20-22 AWG)

- Up to ~5 A → 0.75 mm² (18 AWG)

- 5–10 A → 1.5 mm² (15–16 AWG)


Read more [about wires](https://github.com/kingston-hackSpace/About_wires) here. 

--
## HARDWARE

- Power Supply (voltage and current will depend on the requiremnts of your actuator)

- Arduino board

- IRLZ44N MOSFET (channels high current/voltage from the power supply by following control signals from Arduino)

- Diode 1N4007 or 1N4001 (use to )

- 220ohms resistor (protects Arduino signal pin)

- 1K resistor (grounds Gate to reduce electrical noise)

---
## ELECTRONIC DIAGRAM

⚠️ IMPORTANT NOTE! MOSFET pins have specific functions. See this image to see their order and function.

See diagram here.

---
## ABOUT THE IRLZ44N MOSFET

This is the main component that allow us to channel our 12V from the power supply to the 12V actuator via a Arduino signal (5V).

It can be used as an on/off swtich or control PWM signals (for LED brightness of motor speed control). 

⚠️ The IRLZ44NN MOSFET as safetly handle up to 5A (gets wamr), or 10A if using a heatsink. 




