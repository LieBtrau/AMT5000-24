# Why AM and not FM?
* Higher field strengths are allowed
* Receiver bandwidths are narrower (lower noise floor)
* AM is superior to FM under weak-signal conditions
* AM-band has more usable channels than FM
* construction is less critical because frequencies are low.
* only simple test equipment is needed

# Design choice
* Frequency : 13.56 MHz
  * ISM-band
  * Falls within SW-broadcast band, so COTS AM-receivers can be used
  * Antenna-length is reasonable
  * [Carrier current](https://en.wikipedia.org/wiki/Carrier_current) is possible.  The mains power impedance isn't too low at this frequency.
  * Class-E amplifiers have already been designed for this frequency, for wireless charging.
* Class-E RF amplifier (as on AMT5000)
  * High efficiency
  * Only one switching element
* PWM-modulator using H-bridge IC (as on TR6000)
* Oscillator using ESP32 output using the [LEDC-peripheral](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-reference/peripherals/ledc.html).
* [PWM-generator by ESP32 output](https://docs.espressif.com/projects/esp-iot-solution/en/latest/audio/pwm_audio.html)

