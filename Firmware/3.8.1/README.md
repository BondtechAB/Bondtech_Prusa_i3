
# 3.8.0b Firmware for Bondtech Prusa i3 MK25s / MK3s and MK25s / MK3s Mosquito

2019-10-23

Compiled firmware to support Bondtech Prusa i3 MK25s / MK3s, MK25s / MK3s Mosquito

# 3.8.0b Summery Bondtech specific changes

- Updated mmu.cpp to correct values for E3Dv6, Mosquito and Mosquito Magnum together with the Bondtech extruder when preforming can_load and mmu_load_to_nozzle.
- Changed HEATER_0_MINTEMP for Slice Engineering's High-Temperature thermistor to reduce MINTEMP threshold.



## Changes for MK3s

### MK3s
- #define CUSTOM_MENDEL_NAME "Bondtech-PE MK3s"
- #define BONDTECH_MK3S

- #elif defined(BONDTECH_MK3S)
    current_position[E_AXIS] += 71; //Bondtech_V6 71mm from drive gear to melt zone
- #elif defined(BONDTECH_MK3S)
    current_position[E_AXIS] -= 63; // Pull back 63mm, 8 mm below drive gear
- #elif defined(BONDTECH_MK3S)
    current_position[E_AXIS] += 25.4f; //Bondtech MK2.5s 11 mm longer t melt zone

### MK3s Mosquito
- #define CUSTOM_MENDEL_NAME "Bondtech-M MK3s"
- #define BONDTECH_MOSQUITO

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

- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
      current_position[E_AXIS] += 62; //Bondtech_Mosquito_Magnum 62mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] -= 54; // Pull back 54mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 18.4f; //Bondtech Mosquito Magnum 4 mm longer t melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 21.4f; //7mm further through Mosquito Magnum heat block


## Changes for MK2.5s

### MK2.5s
- #define CUSTOM_MENDEL_NAME "Bondtech-PE MK2.5S"
- #define BONDTECH_MK25S

- #ifdef BONDTECH_MK25S //feed to melt zone
    current_position[E_AXIS] += 71; //Bondtech_V6 71mm from drive gear to melt zone
- #ifdef BONDTECH_MK25S
    current_position[E_AXIS] -= 63; // Pull back 63mm, 8 mm below drive gear
- #ifdef BONDTECH_MK25S
    current_position[E_AXIS] += 25.4f; //Bondtech MK2.5s 11 mm longer t melt zone

### MK2.5s Mosquito
- #define CUSTOM_MENDEL_NAME "Bondtech-M MK2.5S"
- #define BONDTECH_MOSQUITO

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
- #define HEATER_0_MINTEMP 10

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
- #define HEATER_0_MINTEMP 10

- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
      current_position[E_AXIS] += 62; //Bondtech_Mosquito_Magnum 62mm from drive gear to melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] -= 54; // Pull back 54mm, 8 mm below drive gear
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 18.4f; //Bondtech Mosquito Magnum 4 mm longer t melt zone
- #elif defined(BONDTECH_MOSQUITO_MAGNUM)
    current_position[E_AXIS] += 21.4f; //7mm further through Mosquito Magnum heat block
