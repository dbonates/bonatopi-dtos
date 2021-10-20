# Pi Zero GPIO GamePad for BonatoPi - DTO

This overlay configures the gpio pin to work as gamepad firing equivalent keyboard keys.

> Keyboard reference can be found on linux source:
> [https://github.com/torvalds/linux/blob/master/include/uapi/linux/input-event-codes.h](linux-input-event-codes.h)

## Usage

You need to have **dtc** compiler installed. On Mac, you can use _Brew* for it:

```bash
brew install dtc
```

For more info about it, try this link [https://brewinstall.org/install-dtc-on-mac-with-brew/](https://brewinstall.org/install-dtc-on-mac-with-brew/)

### Compile

```perl
dtc -@ -I dts -O dtb -o bonato-pi-gamepad.dtbo bonato-pi-gamepad.dts
```

### Setup

Then copy the `bonato-pi-gamepad.dtbo` to *overlays* dir (usualy /boot/overlays)

and enabled it by appending this line to the /boot/config.txt:

```bash
dtoverlay=bonato-pi-gamepad
```
