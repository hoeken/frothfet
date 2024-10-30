# FrothFET 8CH

### TESTING: 

* Test new drain setup.
* Test PWM on motors and solenoids
  * do we need to change
* test alternate mosfet chips
* test new current sense chips
* Test fan mosfet
  * can we still do tachometer

### Rev E Changes:

* remove pin numbers from esp32
* connect vref and 3.3vadc to 3.3v with solder jumpers
* select pin for channel leds (ws2818)
* channels:
  * re-calculate channel voltage divider
  * change to small ws2812b-2020 chip LED for channel status:  C965555
  * change / add current chip alternates
  * place current filter next to adc?
  * add filter to volt adc - next to adc?
* change to actual terminal block part for channel connections
  * https://www.lcsc.com/product-detail/Barrier-Terminal-Blocks_Cixi-Kefa-Elec-KF78S-13-0-8P_C964541.html
  * Alternatives:
  * https://www.lcsc.com/product-detail/Barrier-Terminal-Blocks_Cixi-Kefa-Elec-KF78CM-13-0-8P_C964692.html
  * https://www.lcsc.com/product-detail/Spring-Clamp-System-Terminal-Block_JILN-JL271R-10004G01_C2917317.html
  * https://www.lcsc.com/product-detail/Spring-Clamp-System-Terminal-Block_Cixi-Kefa-Elec-KF207RB-10-16-4P_C2975094.html
  * https://www.lcsc.com/product-detail/Barrier-Terminal-Blocks_JILN-JL45C-09504B01_C415416.html
