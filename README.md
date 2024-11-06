# klipper-NateHevORT
Klipper settings for my HevORT CoreXY printer

## Tuning notes

### Temp towers
Use `230_PLA_Temp_calibration.stl` https://www.thingiverse.com/thing:2493504. In the slicer, set the temperature in filament settings to the highest temp on the tower - 230 for this example.

Run the below command in the Klipper console. It assumes 0.4 layer height.
`TUNING_TOWER COMMAND='SET_HEATER_TEMPERATURE HEATER=extruder' PARAMETER=TARGET START=230 STEP_DELTA=-5 STEP_HEIGHT=6.8 SKIP=1.2`
