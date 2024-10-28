# Why AM and not FM?
* Higher field strengths are allowed
* Receiver bandwidths are narrower (lower noise floor)
* AM is superior to FM under weak-signal conditions
* AM-band has more usable channels than FM
* construction is less critical because frequencies are low.
* only simple test equipment is needed

# Design choice
* Class-E RF amplifier (as on AMT5000)
* PWM-modulator using H-bridge IC (as on TR6000)
* Oscillator using ESP32 output using the [LEDC-peripheral](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-reference/peripherals/ledc.html).
* [PWM-generator by ESP32 output](https://docs.espressif.com/projects/esp-iot-solution/en/latest/audio/pwm_audio.html)

