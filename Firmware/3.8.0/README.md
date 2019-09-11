
# 3.8.0 Firmware for Bondtech Prusa i3 MK25s / MK3s, MK25s / MK3s Mosquito

2019-09-11

Compiled firmware to support Bondtech Prusa i3 MK25s / MK3s, MK25s / MK3s Mosquito

# Summery Bondtech specific changes

- Variants for Slice Engineerings High temperature thermistor (SE_HT-thermistor)
- Adjusted Load/Unload filament sequence
- MK3s: Changed Z_MAX_POS 205 to allow Z and XYZ calibration
- MK3s: Changed mirostep resolution to 16

##  MK3s Changes

- #define CUSTOM_MENDEL_NAME "Bondtech-PE MK3s"
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define Z_MAX_POS 205
- #define TMC2130_USTEPS_E    16    
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80  

##  MK25s Changes

- #define CUSTOM_MENDEL_NAME "Bondtech-PE MK2.5S"
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80
