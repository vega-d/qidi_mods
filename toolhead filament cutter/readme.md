This mod depends on my custom homing procedure gcode available in the repo.
I recommend you print it out of the toughest material you have. I used 15% carbon fiber PA12 nylon. 

You will need

- 2x M3 10mm long bolts.
- 5mm boxcutter knife blade.
- PC4-M6 bowden tube holder.
- 5.5mm diameter spring.

You will also probably need a drill with 2mm and 3mm drill bits to round the holes, otherwise the printing artifacts may interfere with smooth action. 



klipper macro for unloading filament with this, for x plus 3, for other printers change the coordinates in G1 moves:
```
[gcode_macro UNLOAD_FILAMENT]
gcode:
    {% if printer.extruder.temperature < 210 %}
      M109 S250
    {% endif %}
    {% if printer.toolhead.homed_axes != "xyz" %}
      G28
    {% endif %}
    M117 Unloading Filament...
    G91
    G1 Z5
    G90
    G1 X260 Y10 F10000
    G4 P10
    G1 Y-20
    M83
    FORCE_MOVE STEPPER=extruder DISTANCE=70 VELOCITY=10
    G4 P10
    G1 Y10
    M117 Filament unloaded.
```
