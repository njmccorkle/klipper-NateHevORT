# klipper-NateHevORT
Klipper settings for my HevORT CoreXY printer

## Tuning notes

### Temp towers
Use `230_PLA_Temp_calibration.stl` https://www.thingiverse.com/thing:2493504. In the slicer, set the temperature in filament settings to the highest temp on the tower - 230 for this example.

Run the below command in the Klipper console. It assumes 0.4 layer height.
```
TUNING_TOWER COMMAND='SET_HEATER_TEMPERATURE HEATER=extruder' PARAMETER=TARGET START=230 STEP_DELTA=-5 STEP_HEIGHT=6.8 SKIP=1.2
```

### Pressure advance
See here for Klipper doc: https://www.klipper3d.org/Pressure_Advance.html#tuning-pressure-advance

Use the STL from here: https://www.printables.com/model/123877-klipper-pressure-advance-tower-v2

PrusaSlicer changes:
* Print speed: 100mm/s for 0.4 nozzle. 80mm/s for 0.6.
* Under cooling: Set `Slow down if layer print time is below` to `0`
* Turn off "Lift Z" during retraction

Run the following commands:
```
SET_VELOCITY_LIMIT SQUARE_CORNER_VELOCITY=1 ACCEL=500
TUNING_TOWER COMMAND=SET_PRESSURE_ADVANCE PARAMETER=ADVANCE START=0 FACTOR=.005
```
