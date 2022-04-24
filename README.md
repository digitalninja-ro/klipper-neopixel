# Klipper NeoPixel Templates

## Info

This is a collection of NeoPixel led templates for [Klipper](https://github.com/Klipper3d/klipper) firmware. It uses the array of leds as a progress bar for different printer actions. The refresh rate is faster than delayed_gcode.

The template of NeoPixel is changed by a macro. This is very handy in case you want to change the template during start macro or during a print. For example in the start macro you could set the template for temperature during preheat and then change to the template for print progress or printer speed for the same NeoPixel.

## Installation

1. Assuming you have a working NeoPixel led
   
   ```
   [neopixel my_led]
   pin: PB9
   chain_count: 32
   ```
2. Download / clone ***led_progress.cfg*** to your klipper_config folder

3. Include this file in your printer.cfg

```
[include led_progress.cfg]
```

## Use

```
NEOPIXEL_DISPLAY LED="led_name" TYPE=template_type MODE=template_mode
```
### LED
Your led name from neopixel cfg section

### TYPE

**`extruder_temp`**  extruder temperature relative to target temperature (if is set) or to maxim temperature

**`bed_temp`**  bed temperature relative to target temperature (if is set) or to maxim temperature

**`print_percent`** progress of current print

**`printer_speed`** current speed relative to maximum printer speed

### MODE

`glow` all leds will fade from one color (or non) to an other color

`progress` the leds will light up one by one


You can combine any **TYPE** with any **MODE**.


## Examples

```
NEOPIXEL_DISPLAY LED="my_led" TYPE=extruder_temp MODE=glow
```

This macro command will show the extruder temperature in glow mode.

```
NEOPIXEL_DISPLAY LED="my_led" TYPE=print_percent MODE=progress
```

This macro command will show print completion in progress mode. 

```
NEOPIXEL_DISPLAY LED="my_led" TYPE=print_speed MODE=progress
```

This macro command will show print speed in progress mode.
