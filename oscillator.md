# Oscillator
A crystal could be used, but we won't get better than 10ppm, let's use a TCXO instead.

## Requirements
* 25MHz or 27MHz
* sine wave output
* 3.3V supply
* Less than €2/pce
* frequency tolerance < 2ppm

## Part selection
SX2T25.000B010J020S

# Frequency synthesizer
The ESP32 can generate waveforms at 40MHz and much lower frequencies using the LEDC-peripheral, but the frequency resolution is very limited.  A PLL is required.  The Si5351A will be used:
* cheap
* popular in open-source projects, open-source code is available
* requires external crystal or clock

## Part selection
* Skyworks SI5351A-B-GTR, JLCPCB C504891
* MS5351M : less phase noise, but it's a clone.

# References
[QRP Labs Si5351A Synthesiser Module, PCB Rev 6](https://www.qrp-labs.com/images/synth/synth_assembly6.pdf)