# Oscillator
A crystal could be used, but we won't get better than 10ppm, let's use a TCXO instead.

## Requirements
* Output : not clipped sine wave
  * because the slow edge decreases jitter performance and the duty cycle is not 50%.
* Package : 3.2x2.5mm
  * We need to solder it manually, JLCPCB doesn't have a 25MHz TCXO

## Part selection
* Fox FT3MHUPM25.0-T1
* Abracon ATX-H11-F-25.000MHZ-F25-T

# Frequency synthesizer
The ESP32 can generate waveforms at 40MHz and much lower frequencies using the LEDC-peripheral, but the frequency resolution is very limited.  A PLL is required.  The Si5351A will be used:
* cheap
* popular in open-source projects, open-source code is available
* requires external crystal or clock

## Part selection
* Skyworks Si5351A
* MS5351M : less phase noise

# References
[QRP Labs Si5351A Synthesiser Module, PCB Rev 6](https://www.qrp-labs.com/images/synth/synth_assembly6.pdf)