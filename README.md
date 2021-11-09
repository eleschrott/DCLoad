# DCLoad
### Electronic Direct Current Load
---
THIS IS A FUTURE PROJECT - GROWS BY AND BY - NOT ALL IMPLEMENTED YET!

An electronic load, based on the great work from Louis Scully (http://www.scullcom.uk/).

The original project from Louis was modified to control everything with a Nextion Enhanced 7" LCD-Touchscreen (https://www.itead.cc/wiki/NX8048K070).

With this LCD it's possible to view live data from actual current, voltage, power and resistance as digits, graphical diagram or both. Transient test settings can be view/edit graphical.
The control of the load can be done complete with this touch panel, but a rotary encoder for fast adjustments, buttons to switch ON/OFF and manual trigger also installed. It's possible to save user settings to EEPROM and load them on start.
Give sound feedback on control, response if special values reached, e.g. battery checks. And many more...

Hint: An external supply, e.g. a Laptop Power-Supply with at least 4A is required.
                          
The project is separated in three parts:

  1. The PowerModule    - Provide diffrent voltages for the ohter modules and the Nextion.
  2. The ControlModule  - The MCUs, a real time clock and the interfaces to outside.
  3. The LoadModule     - The load part for the high current, but also the precise voltage generators,
                          the analogue/digital converters and a remote sense control to get exact measurmets.
  
The schematics and the PCB layouts are made with KiCAD (http://kicad.org/).

Three µControllers are working inside:

  - MCU#1, a Teensy 3.1/2 for the HMI (Human Machine Interface) communication with the Nextion, get and set data to view.
    Handle time functions, the external trigger and control the buzzer. Get and set data from/to MCU#2 to control
    the complete load.
  - MCU#2, an Arduino ProMini to control the LoadModule. Get and set data to the ADC/DAC for adjusting the load, get data from
    remote sense and also from the temperature sensor. Control the fan for cooling the load.
  - MCU#3, an ATtiny85 shifts the pwm frequncy for the fan to a higher range to work in "silent mode" (above 32kHz).

  The MCUs #1 & #2 communicate together with a SPI bus, each of them talk with I2C to the controlled parts.
  The Nextion Display gets and send data over a serial communication to the Teensy.

For future developments, some (actual unused) interfaces are implemented and the MCUs has some hardware wires to react direct together.
