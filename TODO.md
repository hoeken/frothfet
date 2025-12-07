# FrothFET 8CH

#### Case Design

* add fuse holders
  * make it an insertable box
  * 1 x mega
  * 3 x ATC

#### Rev F

* remove 0402 and 0805 parts from adc reg
* change part to XFCN 508 instead of 507
* change all leds to green
* other layout / placement tweaks
* check all silkscreens
* test bom and placement
  
#### Rev F Done

* pulled in updated esp32-s3 schematic
* remove adc vref schematic
* remove mcp3526r adc schematic
* remove bleed circuit
* change to ina226 w/ 2mOhm / 3920 shunt resistor (C5224159, ASR-F-5-2F, etc)
* move bypass fuse to only bypass mosfet.  shunt resistor should be solid
* add 3.3v to 5.0v level shifter for rgb leds
* add buffer to pwm pins: 74VHC540FT (or 74VHC541FT) or 74LVC540A (74LVC541A also works)
  * 4 options, all tssop-20 package, interchangeable except for normal/inverting
  * choose the most common / cheapest and all good
  * add output enable pin from esp32-s3 to buffer
  * also needs its own pullup resistor to keep it off during boot
  * add pullup resistors to output of buffer to keep mosfets off during boot
* usb 5v does not power ADC, buzzer, etc. (pull idea diode circuit from brineomatic)
* add test points for 3.3v, 5.0v, 24v, gnd, sda, scl, mosfet gate, load+, etc.
* all test points -> 1.5x0.7mm
* add qwiic connector
* added generic pin header  
* switch to SMTSO3080CTJ for mounting holes - top
* change to 3 separate fuse clips for channel fuse (C41371870)
* temperature sensor should have copper from the power trace running underneath
* changed pulldown to pullup on LM74502H OV pin (pwm)
* added support for ALERT pin from INA226 for overcurrent protection (hopefully)