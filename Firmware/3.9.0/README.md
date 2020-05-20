
#3.9.0 Firmware for Bondtech Prusa i3 MK25 / MK3,  MK25s / MK3s and MK25s / MK3s Mosquito

2020-05-20

Compiled firmware to support Bondtech Prusa i3 MK25 / MK3, MK25s / MK3s, MK25s / MK3s Mosquito

Firmware based on Prusa's latest release with adjustments to support bondtech extruders. Please read Prusa's release note for all changes in the new release: https://github.com/prusa3d/Prusa-Firmware/releases/tag/v3.9.0

# 3.9.0 Summary Bondtech specific changes

- Variants for Slice Engineering's High temperature thermistor (SE_HT-thermistor).
- Adjusted Load/Unload filament sequence.
- MK3/MK3s: Changed microstep resolution to 16.
- MK3s/MK25s: Correct Z_MAX_POS adjustemts to allow XYZ Calibration.
- MK3s/Mk25s: Adjusted mmu.cpp to correct values for E3Dv6, Mosquito and Mosquito Magnum together with the Bondtech extruder when preforming can_load and mmu_load_to_nozzle.
- Now with multi language support.

Source Code: https://github.com/BondtechAB/Bondtech-Prusa-Firmware
