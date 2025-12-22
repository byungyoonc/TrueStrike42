# TrueStrike42
TrueStrike42 is a columnar staggered unibody split Hall effect keyboard designed to maximize performance and minimize finger fatigue.

# Layout
![](doc/res/truestrike42-kle.png)

# How to build
Please read the [build guide](doc/buildguide.md).

# Firmware
## Use precompiled binary
Flash `fw/truestrike42_via.uf2` to your RP2040-based development board when it is in a bootloader state.

## Build on your own
### Option A
Copy `fw/truestrike42` folder into your cloned QMK Firmware repository's `keyboards` folder, then run `qmk compile -kb truestrike42 -km via`.

### Option B
- [QMK Firmware fork](https://github.com/byungyoonc/qmk_firmware/tree/Truestrike42)
- [VIA QMK Userspace fork](https://github.com/byungyoonc/qmk_userspace_via/tree/truestrike42)

Above are branches of QMK Firmware/Userspace repository which supports firmware compilation for TrueStrike42. 

Follow [this guide for External QMK Userspace](https://docs.qmk.fm/newbs_external_userspace) to build on your own.

# Using VIA HE Configurations
The following tools can be accessed via VIA's **HE TOOLS** menu, next to the **LIGHTING** entry.

## Load VIA Definition
Load the draft definition `fw/truestrike42.json` in the **DESIGN** tab in VIA to use VIA with TrueStrike42.

## Calibrations
**Make sure to run the calibration at least once before using the keyboard!**
### Bottoming Calibration
Calibrates magnetic flux values for each sensors, when each switches are entirely bottomed out.

Turn on the toggle, then bottom out every single switches. Turn off the toggle.

### Noise Floor Calibration
Calibrates how much the magnetic flux value fluctuates because of background noise.

Click once while doing absolutely nothing with the keyboard. The firmware will sample the magnetic flux value for certain short amount of time to figure out the noise bottom level.

### Show Calibration Data
Prints out current calibration data to the debug console.

### Clear Bottoming Calibration Data
Resets Bottoming Calibration Data to make new calibration. Use this when you replace your Hall Effect switches to the different ones.

## Actuation
### Mode
Choose between APC and Rapid Trigger.

APC works like the traditional digital switch, but you can change where does the actuation/release happens.

Rapid Trigger tracks the height of the switch to figure out whether the key is being pressed down or released up.

### Offsets
Sets the offset values for corresponding Mode you chose.

The value starts from 1(Topmost) to 255(Bottommost).

# Copyright Notice
`True-Strike-icon.kicad_mod` was created by modifying an icon image for True Strike in a game Baldur's Gate 3, a game by Larian Studios. I used it under the [Larian Fan Content Policy](https://larian.com/fan-content-policy).