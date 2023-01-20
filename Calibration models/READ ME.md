# Calibration models
These models are used to help calibrate different parameters and settings of the printer

## Temperature tower
[FILE](Temperature_Tower.stl) [SOURCE](https://www.thingiverse.com/thing:3064519)
This file is used to calibrate the temperature which is best for the given filament and feed rate.

For use with prusa slicer as of v2.5.0 the following GCODE needs to be added to "After layer change GCODE" in the printer settings tab
```GCODE
;AFTER_LAYER_CHANGE
{if layer_z <= 1}M104 S230
{elsif layer_z <= 6}M104 S230
{elsif layer_z <= 11}M104 S225
{elsif layer_z <= 16}M104 S220
{elsif layer_z <= 21}M104 S215
{elsif layer_z <= 26}M104 S210
{elsif layer_z <= 31}M104 S205
{elsif layer_z <= 36}M104 S200
{elsif layer_z <= 50}M104 S195
{endif}
;[layer_z]
```
[SOURCE](https://projects.ttlexceeded.com/3dprinting_prusaslicer_gcode.html#other-custom-g-code)