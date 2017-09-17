# DCLoad
Electronic Dicect Current Load

An electronic load, based on the work from Louis Scully (http://www.scullcom.uk/).

The original project from Louis was modified to control everything with a Nextion Enhanced 7" LCD-Touchscreen.
With this LCD it's possible to view live data from actual current, voltage, watt and resistance as digits, graphical diagramm or both. The control can be done complete with this touch panel, but a rotay encoder for fast anjustments, buttons for ON/OFF and manual trigger also installed. It's possible to save user settings to EEPROM and load them on start. Give sound response if special values reached, e.g. battery checks. And many more...

The project is separated in three parts:

  1. The PowerModule    - Everything for power supply.
  2. The ControlModule  - The MCUs, the RTC and the links to the outside.
  3. The LoadModule     - The load part for the high current, but also the precised volage generators and
                          analog/digital converters.
  
The schematics and the pcb layouts are made with KiCAD (http://kicad-pcb.org/).

Two µControllers works inside:

  - MCU#1, a Teensy 3.1/2 for the HMI (Human Machine Interface) like communication with the Nextion, get and set data to view.
    Hanlde the external trigger and control the buzzer. Get and set data from/to MCU#2.
  - MCU#2, a Arduino ProMini to control the LoadModule. Get and set data to the ADC/DAC on the load. from the temp. sensor
    and control the fan.
    
  The MCUs communicate together with SPI, each of them with I2C with the controlled parts.


  
