# Controlling 5-12V devices with Arduino

This guide describes how to build the electronic circuit to use/trigger/control 12V devices (motors, fans, pumps, LED strips) with Arduino boards.

ALTERNATIVE TRANSISTOR TIP120 (old school electronic component)

-----
### Why it matters

- 12V DEVICE

Arduino pins can provide up to 5V into actuators. You can still use Arduino to control a 12V device, but it will require additional electronic components and a 12V power supply that will manage building a safe powering circuit. 

- 5V HIGH CURRENT DEVICE

This also applies if your actuator is 5V but high current. Arduino pins can provide ~20mA (for example, a 5V LED strip of many leds). Despite being 5V, the high current will cause overheat and can cause a fire, melting the wires and eventurallu creating a electrical hazard (electroshock or short circuiting the wiring). This is extremely dangerous.  

*NOTE: Arduino **VIN pin** stands for "Voltage-IN", supporting up to 12V. However, this is not an output pin, it works only as an alteranative board powering pin.* 

--
## IMPORTANT! WIRE TYPE!

- PENDING /////////////////////////////////////

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

IMPORTANT NOTE! MOSFET pins have specific functions. See this image to see their order and function.

See diagram here.

---
## ABOUT IRLZ44NN MOSFET

This is the main component that allow us to channel our 12V from the power supply to the 12V actuator via a Arduino signal (5V).

It can be used as an on/off swtich or for PWM signals. 

The IRLZ44NN MOSFET as safetly handle up to 5A (gets wamr), or 10A if using a heatsink. 




