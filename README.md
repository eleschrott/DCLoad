# DCLoad
Electronic load for dircet current

An electronic load, based o the work from Louis Scully (http://www.scullcom.uk/).

Modified to control everything with a Nextion Enhanced 7" LCD-Touchscreen.
With this LCD it's possible to view live data from actual current, voltage, watt and resistance as digits, graphical diagramm ore both. All control can be done with this touch panel, an rotay encoder is also installed for fast anjustments.
Saving user setting data to EEPROM and load them on start. Give sound response if special values reached, e.g. battery checks.
And many more...

The project is split in three parts:

  1. The PowerModule    - Everythin for the power supply.
  2. The ControlModule  - Heres the MCUs and the links to the outside.
  3. The LOADModule     - The load part for the high current, but also the precised volage generators and
                          analog/digital converters.
  
  Everything, the schematics and the pcb layouts are made with KiCAD (http://kicad-pcb.org/).
