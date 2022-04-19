# Klipper NeoPixel Templates

## Info

This is a collection of NeoPixel led templates for [Klipper](https://github.com/Klipper3d/klipper) firmware. It uses the array of leds as a progress bar for different printer actions. The refresh rate is faster than delayed_gcode.

The template of NeoPixel is changed by a macro. This is very handy in case you want to change the template during start macro or during a print. For example in the start macro you could set the template for temperature during preheat and then change to the template for print progress or printer speed for the same NeoPixel.

## Instalation

1. Assuming you have a working NeoPixel led

2. Download / clone ***led_progress.cfg*** to your klipper_config folder

3. Include this file in your printer.cfg
   
   ```
   [include led_progress.cfg]
   ```

## Use

```
NEOPIXEL_DISPLAY LED=Led_Name TEMPLATE=template_name
```




Available templates:

**`led_extruder_temp`** current extruder temperature relative to target temperature (if is set) or to maxim extruder temperature

**`led_bed_temp`** current bed temperature relative to target temperature (if is set) or to maxim bed temperature

**`led_print_progress`** progress of current print

**`led_printer_speed`** current speed relative to maximum printer speed
