# FrothFET 8CH

FrothFET notes:

* debug / test MCP3564R
  * read the datasheet and make notes
  * analyze each command and response
  * connect IRQ, MCLK to esp32
* test ADS1115 chips
  * connect ALERT/RDY to esp32
* Test maximum current on MOSFETs
* Test fully loaded
* determine if we will keep the ADC regulator - measure DC
* determine if we will keep the ADC vref
* switch fans to simple on/off control
  * do we need tachometer?

TODO: 

* dnp the "filter" on the gate drive
* change the voltage divider resistors for 3.3v vref
* add a 'pulldown' mosfet for faster switching?
* add power LEDs
* update the MCP1754 schematic with 2 1uF caps in/out, drop the inductor
* 4.5mm holes in the +pos connectors
* add alarm buzzer