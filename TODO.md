# FrothFET 8CH

### Rev E Changes:

* remove pin numbers from esp32
* connect vref and 3.3vadc to 3.3v with solder jumpers
* select pin for channel leds (ws2818)
* channels 5/6 turn on during code upload - change pins?  add pulldown resistors to all PWM pins?
* channels:
  * re-calculate channel voltage divider <= 30k and 3.3v output
  * change / add current measurement chip alternates
  * place current filter next to adc?
  * add filter to volt adc - next to adc?
  * recalculate values for adc filters - 1khz should be fine
* change to actual terminal block part for channel connections
  * https://www.lcsc.com/product-detail/Barrier-Terminal-Blocks_Cixi-Kefa-Elec-KF78S-13-0-8P_C964541.html
  * Alternatives:
  * https://www.lcsc.com/product-detail/Barrier-Terminal-Blocks_Cixi-Kefa-Elec-KF78CM-13-0-8P_C964692.html
  * https://www.lcsc.com/product-detail/Spring-Clamp-System-Terminal-Block_JILN-JL271R-10004G01_C2917317.html
  * https://www.lcsc.com/product-detail/Spring-Clamp-System-Terminal-Block_Cixi-Kefa-Elec-KF207RB-10-16-4P_C2975094.html
  * https://www.lcsc.com/product-detail/Barrier-Terminal-Blocks_JILN-JL45C-09504B01_C415416.html
* change to smaller smt components: 0603 where possible
* implement esp32-s3 dev module onto the board (re-draw waveshare module)
* change to M/F standoffs + captive nuts or heat press inserts
* can we move mounting holes to allow for symmetric case design?
* see what improvements can be made for noise and ADC routing.