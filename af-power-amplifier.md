# Amplifier
## PWM input
A fully digital signal path is used.  The ESP32 generates the PWM signal using the [PWM-audio component](https://docs.espressif.com/projects/esp-iot-solution/en/latest/audio/pwm_audio.html).  The PWM signal is fed to a half-bridge IC, which drives the speaker.

### Audio bandwidth
The audio bandwidth of an AM-receiver (e.g. Qodosen DX-286) is only 3kHz.  AM-broadcast transmitters have frequency spacings of 9 or 10kHz, depending on the continent.  By using an 8kHz sampling rate, the audio bandwidth is limited to 4kHz.  This is sufficient for AM-reception.

### PWM frequency & resolution
[PWM Distortion Analysis](http://www.openmusiclabs.com/learning/digital/pwm-dac/pwm-distortion-analysis/).  Key takeaways are :
* PWM is multiplication of your audio signal with a square wave at the PWM frequency
* Harmonics of the PWM frequency are generated
* Harmonics of the audio frequency are generated as well, because the audio signal isn't continuous, but a series of samples, sampled at the PWM frequency.
* Phase correct PWM has less (around 25dB) distortion than fast PWM
* PWM frequency should be at least 7 to 10 times the audio frequency

The ESP32 audio component only supports up to 48kHz PWM frequency.  This is sufficient for an audio bandwidth of 4kHz.  The resolution of the PWM signal is 10 bits (limited by the 80MHz APB clock of the ESP32).  This is sufficient for an audio SNR of 62dB.

### Half-bridge IC
[CSD97395Q4M](https://www.ti.com/lit/ds/symlink/csd97395q4m.pdf) is a half-bridge IC with a 60A peak current.  It's available on JLCPCB.
The minimum ON-time is 40ns.

### Reconstruction filter
The PWM signal is fed to a low-pass filter to remove the PWM frequency and its harmonics.  The filter is a 2nd order Butterworth filter with a cutoff frequency of 6kHz, designed by [Markimicrowave](https://markimicrowave.com/technical-resources/tools/lc-filter-design-tool/).  The filter is designed for a 1ohm load impedance.
* L = 39µH → L = Wuerth 744776139 (lowest loss at 13.56MHz)
* C = 39µF → 4x 10µF, 1210 package

## Analog input
An alternative to generating audio by PWM is using a single ended class D amplifier with analog audio input.  The MP7741 is such a device.  It's not available on JLCPCB.

## I2S input
This would be the ideal option.  A single ended class D amplifier with I2S input.  Unfortunately, all I2S amplifiers I found had balanced audio outputs.