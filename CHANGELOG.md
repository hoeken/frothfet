## Rev F Release Notes

### **Power & Regulation**
* **5V Regulator:** Switched to **RT7272B** (ported from Brineomatic).
* **USB Power:** USB 5V now powers the ADC, buzzer, etc.
* **Traces:** Beefed up 5V traces and added a partial 3.3V power plane.
* **Level Shifting:** Added 3.3V to 5.0V level shifter for RGB LEDs.

### **Control & Logic**
* **ESP32-S3:** Pulled in updated schematic.
* **PWM Buffers:** Added buffer to PWM pins for better MOSFET control.
    * *Accepted parts:* 74VHC540FT, 74VHC541FT, 74LVC540A, or 74LVC541A (TSSOP-20).
    * Added Output Enable (OE) pin from ESP32-S3 to buffer (with pullup resistor to keep disabled during boot).
    * Added pullup resistors to buffer outputs to ensure MOSFETs remain off during boot.
* **OV Pin:** Changed pulldown to **pullup** on the LM74502H OV pin (PWM).

### **Sensing & ADC**
* **Current Sensing:** Switched to **INA226** with 2mΩ / 3920 shunt resistor (C5224159, ASR-F-5-2F, etc.).
    * Added support for the **ALERT** pin from INA226 for overcurrent protection.
* **Temp Sensor:** Improved thermal coupling; sensor now has copper from the power trace running underneath.
* **Clean-up:** Removed old ADC VREF, MCP3526R ADC schematic, and bleed circuit.

### **Protection & Safety**
* **Fuses:**
    * Changed to 3 separate fuse clips for the channel fuse (C41371870).
    * Moved bypass fuse to only bypass the MOSFET; the shunt resistor is now solid.
* **ESD:** Added ESD protection to each channel output.

### **Connectors & Mechanical**
* **Mounting:** Switched to **SMTSO3080CTJ** for mounting holes.
* **Connectors:**
    * Added **Qwiic** connector.
    * Added generic pin header.
    * Changed to **XFCN 507** (replaced JLC unavailable part).
* **Test Points:**
    * Added test points for 3.3V, 5.0V, 24V, GND, SDA, SCL, MOSFET Gate, Load+, etc.
    * Standardized all test points to 1.5 x 0.7mm.
    
## Rev E

Upgrades based on real world usage of the Rev D.  Changes include:

* switched to on-board esp32-s3 instead of devkit module
* changed to LM74502H gate driver to bring price down (about $2 vs $6)
* added WS2812B leds to each channel for more informative channel status
* fixed error with adc irq being unconnected
* added piezo buzzer
* changed to TPS7A2033 adc voltage regulator and REF3533 voltage reference chips
* added a few extra ESD and overvoltage protections
* changed to actual barrier screw terminals for positive connections
* positive busbar now longer so cables can safely come out the bottom of board as well as sides
* fan control now has an on/off mosfet in addition to pwm for using simple 2 or 3 wire fans
* changed to TMCS1108 for current measurement due to supply issues

## Rev D

Biggest change is moving to the LTC7004 gate driver chip to enable PWM control and a switch to N-channel mosfets.

Some other changes:

* Switched to a 4 layer PCB
* Added individual channel voltage monitoring
* Added separate ADC VCC regulator