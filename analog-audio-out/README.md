# Pi Zero PWM Audio - DTO

This overlay configures the gpio-alt functions on the fly to remap the audio-pwm pins from hidden ones to pins on the gpio-pinheader.

This maps the left channel to BCM 13 and the right channel BCM 18

## Usage

You need to have **dtc** compiler installed. On Mac, you can use _Brew* for it:

```bash
brew install dtc
```

For more info about it, try this link [https://brewinstall.org/install-dtc-on-mac-with-brew/](https://brewinstall.org/install-dtc-on-mac-with-brew/)

### Compile

```perl
dtc -@ -I dts -O dtb -o pwm-audio-2chan.dtbo pwm-audio-2chan.dts
```

### Setup

Then copy the `pwm-audio-2chan.dtbo` to *overlays* dir (usualy /boot/overlays)

and enabled it by appending this line to the /boot/config.txt:

```bash
dtoverlay=pwm-audio-2chan
```
