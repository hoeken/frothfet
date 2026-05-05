# FrothFET 8CH

## Rev G

* update the current shunt footprint based on datasheet

# FrothFET Mini

## Rev A

* 16 x 3A loads / 40A max
* order potential connectors to test
* passive / pwm buzzer
* use same rgb led for status
* use BTS724G for load drivers
* use PCA9685 for pwm / control
* use ina226 w/ new resistor for voltage/current
* 2920 ptc fuse - 3A / 30v+. eg. C18203127
* no temperature sensing
* no bypass mode
* no fans / tachometers
* how to handle alert mode for 16 ina226 chips?
  * 16 interrupts
* overcurrent protection from BTS724G instead?
  * BTS724G also has diagnostic outputs - 2 per chip / 8 total
  * Maybe use an 8-pin gpio expander?
  * looks like this diagnostic just alerts on open load