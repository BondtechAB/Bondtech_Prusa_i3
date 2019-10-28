
# 3.8.1 Firmware for Bondtech Prusa i3 MK25 / MK3,  MK25s / MK3s and MK25s / MK3s Mosquito

2019-10-28

Compiled firmware to support Bondtech Prusa i3 MK25 / MK3, MK25s / MK3s, MK25s / MK3s Mosquito

Firmware based on Prusa's latest release with adjustments to support bondtech extruders. Please read Prusa's release note for all changes in the new release: https://github.com/prusa3d/Prusa-Firmware/releases/tag/v3.8.1

# 3.8.1 Summery Bondtech specific changes

- Variants for Slice Engineerings High temperature thermistor (SE_HT-thermistor)
- Adjusted Load/Unload filament sequence
- MK3/MK3s: Changed mirostep resolution to 16
- MK3s/MK25s: Changed Z_MAX_POS 205 to allow Z and XYZ calibration
- MK3s/Mk25s: Adjusted mmu.cpp to correct values for E3Dv6, Mosquito and Mosquito Magnum together with the Bondtech extruder when preforming can_load and mmu_load_to_nozzle.


## Changes for MK3

### MK3
- #define CUSTOM_MENDEL_NAME "Bondtech-PE MK3"
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define TMC2130_USTEPS_E    16
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80

### MK3s
- #define CUSTOM_MENDEL_NAME "Bondtech-PE MK3s"
- #define BONDTECH_MK3S
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define TMC2130_USTEPS_E    16
- #define Z_MAX_POS 205
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80

- #elif defined(BONDTECH_MK3S)
    current_position[E_AXIS] += 71; //Bondtech_V6 71mm from drive gear to melt zone
- #elif defined(BONDTECH_MK3S)
    current_position[E_AXIS] -= 63; // Pull back 63mm, 8 mm below drive gear
- #elif defined(BONDTECH_MK3S)
    current_position[E_AXIS] += 25.4f; //Bondtech MK2.5s 11 mm longer t melt zone

### MK3s Mosquito
- #define CUSTOM_MENDEL_NAME "Bondtech-M MK3s"
- #define BONDTECH_MOSQUITO
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define TMC2130_USTEPS_E    16  
- #define Z_MAX_POS 205  
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80  

- #elif defined(BONDTECH_MOSQUITO)
    current_position[E_AXIS] += 70; //Bondtech_Mosquito 70mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO)
    current_position[E_AXIS] -= 62; // Pull back 62mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO)
    current_position[E_AXIS] += 23.4f; //Bondtech Mosquito 9 mm longer t melt zone
- #ifdef BONDTECH_MOSQUITO
    current_position[E_AXIS] += 16.4f; //2mm further through Mosquito heat block

### MK3s Mosquito Magnum
- #define CUSTOM_MENDEL_NAME "Bondtech-MM MK3s"
- #define BONDTECH_MOSQUITO_MAGNUM
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define TMC2130_USTEPS_E    16   
- #define Z_MAX_POS 205
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80  

- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 62; //Bondtech_Mosquito_Magnum 62mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] -= 54; // Pull back 54mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 18.4f; //Bondtech Mosquito Magnum 4 mm longer t melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 21.4f; //7mm further through Mosquito Magnum heat block

### MK3s Mosquito with high temperature thermistor (SliceE_HT)
- #define CUSTOM_MENDEL_NAME "Bondtech-M MK3s-HT "
- #define BONDTECH_MOSQUITO
- #define HEATER_0_MINTEMP 5
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define TMC2130_USTEPS_E    16    
- #define Z_MAX_POS 205
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80  

- #elif defined(BONDTECH_MOSQUITO)
    current_position[E_AXIS] += 70; //Bondtech_Mosquito 70mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO)
    current_position[E_AXIS] -= 62; // Pull back 62mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO)
    current_position[E_AXIS] += 23.4f; //Bondtech Mosquito 9 mm longer t melt zone
- #ifdef BONDTECH_MOSQUITO
    current_position[E_AXIS] += 16.4f; //2mm further through Mosquito heat block

### MK3s Mosquito Magnum with high temperature thermistor (SliceE_HT)
- #define CUSTOM_MENDEL_NAME "Bondtech-MM MK3s-HT"
- #define BONDTECH_MOSQUITO_MAGNUM
- #define HEATER_0_MINTEMP 5
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define TMC2130_USTEPS_E    16  
- #define Z_MAX_POS 205  
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80  

- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
      current_position[E_AXIS] += 62; //Bondtech_Mosquito_Magnum 62mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] -= 54; // Pull back 54mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 18.4f; //Bondtech Mosquito Magnum 4 mm longer t melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 21.4f; //7mm further through Mosquito Magnum heat block


## Changes for MK2.5

### MK2.5
- #define CUSTOM_MENDEL_NAME "Bondtech-PE MK2.5"
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80

### MK2.5s
- #define CUSTOM_MENDEL_NAME "Bondtech-PE MK2.5S"
- #define BONDTECH_MK25S
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define Z_MAX_POS 205
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80

- #ifdef BONDTECH_MK25S //feed to melt zone
    current_position[E_AXIS] += 71; //Bondtech_V6 71mm from drive gear to melt zone
- #ifdef BONDTECH_MK25S
    current_position[E_AXIS] -= 63; // Pull back 63mm, 8 mm below drive gear
- #ifdef BONDTECH_MK25S
    current_position[E_AXIS] += 25.4f; //Bondtech MK2.5s 11 mm longer t melt zone

### MK2.5s Mosquito
- #define CUSTOM_MENDEL_NAME "Bondtech-M MK2.5S"
- #define BONDTECH_MOSQUITO
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define Z_MAX_POS 205
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80

- #elif defined(BONDTECH_MOSQUITO)
    current_position[E_AXIS] += 70; //Bondtech_Mosquito 70mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO)
   current_position[E_AXIS] -= 62; // Pull back 62mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO)
   current_position[E_AXIS] += 23.4f; //Bondtech Mosquito 9 mm longer t melt zone
- #ifdef BONDTECH_MOSQUITO
   current_position[E_AXIS] += 16.4f; //2mm further through Mosquito heat block

### MK2.5s Mosquito Magnum
- #define CUSTOM_MENDEL_NAME "Bondtech-MM MK2.5S"
- #define BONDTECH_MOSQUITO_MAGNUM
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define Z_MAX_POS 205
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80

- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
      current_position[E_AXIS] += 62; //Bondtech_Mosquito_Magnum 62mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] -= 54; // Pull back 54mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 18.4f; //Bondtech Mosquito Magnum 4 mm longer t melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 21.4f; //7mm further through Mosquito Magnum heat block

### MK2.5s Mosquito with high temperature thermistor (SliceE_HT)
- #define CUSTOM_MENDEL_NAME "Bondtech-M MK2.5S-HT"
- #define BONDTECH_MOSQUITO
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define HEATER_0_MINTEMP 10
- #define Z_MAX_POS 205
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80

- #elif defined(BONDTECH_MOSQUITO)
    current_position[E_AXIS] += 70; //Bondtech_Mosquito 70mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO)
   current_position[E_AXIS] -= 62; // Pull back 62mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO)
   current_position[E_AXIS] += 23.4f; //Bondtech Mosquito 9 mm longer t melt zone
- #ifdef BONDTECH_MOSQUITO
   current_position[E_AXIS] += 16.4f; //2mm further through Mosquito heat block

### MK2.5s Mosquito Magnum with high temperature thermistor (SliceE_HT)
- #define CUSTOM_MENDEL_NAME "Bondtech-MM MK2.5S-HT"
- #define BONDTECH_MOSQUITO_MAGNUM
- #define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
- #define HEATER_0_MINTEMP 10
- #define Z_MAX_POS 205
- #define LOAD_FILAMENT_1 "G1 E80 F400"
- #define UNLOAD_FILAMENT_1 "G1 E-95 F7000"
- #define FILAMENTCHANGE_FINALRETRACT -95
- #define FILAMENTCHANGE_FIRSTFEED 80

- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
      current_position[E_AXIS] += 62; //Bondtech_Mosquito_Magnum 62mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] -= 54; // Pull back 54mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 18.4f; //Bondtech Mosquito Magnum 4 mm longer t melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 21.4f; //7mm further through Mosquito Magnum heat block
