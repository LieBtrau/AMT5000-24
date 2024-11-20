# Why AM and not FM?
* Higher field strengths are allowed
* Receiver bandwidths are narrower (lower noise floor)
* AM is superior to FM under weak-signal conditions
* AM-band has more usable channels than FM
* construction is less critical because frequencies are low.
* only simple test equipment is needed

# Design choice
* DfM (Design for Manufacturability)
  * Use of COTS components
  * Use of standard PCB manufacturing techniques, no coil winding
  * Use of standard assembly techniques, preferably SMT
  * Ease of patching : SOIC instead of TSSOP
* Frequency : 13.56 MHz
  * ISM-band
  * Falls within SW-broadcast band, so COTS AM-receivers can be used
  * Antenna-length for a dipole is reasonable
  * [Carrier current](https://en.wikipedia.org/wiki/Carrier_current) is possible.  The mains power impedance isn't too low at this frequency.
  * 13.56MHz Class-E power amplifier designs is not uncommon
* Output power : 5W
  * remains within QRP limits

# Block diagram
<img src="./images/AM-transmitter_blockDiagram.png" width="1000"/>

High-level AM-generator block diagram

## RF-section (Radio-frequency)
* [Crystal Oscillator & frequency synthesizer](./oscillator.md)
* [Buffer amplifier & RF-power amplifier](./rf-amp.ipynb)

## AF-section (Audio-frequency)
* Audio PWM-modulator using H-bridge IC (as on TR6000) : CSD97395Q4M
* [PWM-generator by ESP32 output](https://docs.espressif.com/projects/esp-iot-solution/en/latest/audio/pwm_audio.html)

## Modulator
Modulation happens by the output of the PWM-generator being used as power supply for the RF-power amplifier.

## Output filter
The output filter suppresses the harmonics of the switching frequency of the RF-power amplifier.