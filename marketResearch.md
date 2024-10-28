# Hobby circuits
* [How to Build an AM Radio Transmitter](https://www.circuitbasics.com/amplitude-modulated-transmitters/)
  * Colpitts oscillator in final stage.  Audio modulates the oscillator.
* [Build an AM Transmitter for Use with Antique Radios](https://www.nutsvolts.com/magazine/article/build-an-am-transmitter-for-use-with-antique-radios)
  * All linear circuits, no switching going on here.
* [M0DAD The Poppet](http://www.geocities.ws/raiu_harrison/mwa/tech/circuits/poppet.html)
  * Class-C amplifier
* [A simple AM modulator](https://www.giangrandi.org/electronics/am-mod/am-mod.shtml)
  * Class-C amplifier
* [FAT5 AM Transmitter](https://www.s9plus.com/index.html)
  * AM-transmitter in modules : Class E RF-amp, modulator (linear or PWM), oscillator

# Transmitter evaluation
## AM88
* Described in : "Build Your Own Low-Power Transmitters: Projects for the Electronics Experimenter by Rudolf F. Graf", §5. PLL Synthesized AM Transmitter for 530-1710 kHz
* 12VDC power supply
* AGC circuit
* PLL circuit could be replaced by MCU
* Chebychev output for filtering 2nd harmonic.  3 filters needed for 150kHz-1.8MHz range.

## DT6000
* [improved transmitter over AMT3000 and AMT5000](https://github.com/TransmitterPlans/DT6000-Transmitter-Files-)
  * [SSTRAN AMT-3000 am transmitter](http://www.radiomanual.info/schemi/Surplus_Radioamateur/SStran_AMT-3000_user.pdf)
  * [SSTRAN AMT-5000 ](https://github.com/TransmitterPlans/DT6000-Transmitter-Files-/blob/main/340473333-AMT5000Manual-R1-20110918-1106PM.pdf)
* Schematic is hard to read.
* includes antenna building info in appendix
* Uses AMT3000 audio / RF sections 
* 100mW
* AD9833 : DDS square wave generator
* ATMega328 control

## Wenzel
* [AM-transmitter](https://techlib.com/electronics/amxmit.htm)
* Low Power
* Also contains antenna tuning info
* LPAM handbook (includes antenna building info)