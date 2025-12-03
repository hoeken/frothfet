# FrothFET 8CH

#### Case Design

* add fuse holders
  * make it an insertable box
  * 1 x mega
  * 3 x ATC

#### Rev F

* usb 5v does not power ADC, buzzer, etc.
* remove rtc clock
* remove bleed circuit
* remove adc vref
* remove mcp3526r
* add buffer to pwm pins: 74VHC540FT (or 74VHC541FT) or 74LVC540A (74LVC541A also works)
  * 4 options, all tssop-20 package, interchangeable except for normal/inverting
  * choose the most common / cheapest and all good
  * add output enable pin from esp32-s3 to buffer
  * also needs its own pullup resistor to keep it off during boot
  * add pullup resistors to output of buffer to keep mosfets off during boot
* change to ina226 w/ 2mOhm / 3920 shunt resistor (C5224159, ASR-F-5-2F, etc)
* move bypass resistor to only bypass mosfet.  shunt resistor should be solid
* add temperature sensor close to current sense resistor or mosfet (LM75BDP)
  * temperature sensor should have copper from the power trace running underneath
* switch to SMTSO3080CTJ for mounting holes - top
* add 4x mount holes for board to case bottom - just in case
* add test points for 3.3v, 5.0v, 24v, gnd, sda, scl, mosfet gate, load+, etc.
* all test points -> 1.5x0.7mm
* add a decent sized bulk capacitor on 24v - 220uF / 50v
* add 3.3v to 5.0v level shifter for rgb leds: TI SN74LV1T34DBVR
  * also add a series resistor on output just in case (0 ohm)
* extra IO
  * add qwiic connector
  * add spi connector
  * add ttl connector
  * or just a generic pin header
  
#### Rev F Done

* pulled in updated esp32-s3 schematic
  
##### I2C Addresses:

* 1000000 - ina226 ch1 - 3pf
* 1000001 - ina226 ch2
* 1000010 - ina226 ch3
* 1000011 - ina226 ch4
* 1000100 - ina226 ch5
* 1000101 - ina226 ch6
* 1000110 - ina226 ch7
* 1000111 - ina226 ch7
* 1001000 - lm75 ch1 - 20pf
* 1001001 - lm75 ch1
* 1001010 - lm75 ch1
* 1001011 - lm75 ch1
* 1001100 - lm75 ch1
* 1001101 - lm75 ch1
* 1001110 - lm75 ch1
* 1001111 - lm75 ch1
* 1101000 - bus voltage - 10pf
