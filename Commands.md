Startup
=======

M502          ; Reset settings to configuration defaults...
M250 C135     ; Set contrast
M851 Z-3.32   ; Reset Z0Offset
M500          ; ...and Save to EEPROM. Use this on a new install.
M501          ; Read back in the saved EEPROM.



Z-Offset
========

1. G28          ; Home
2. M851 Z0      ; Reset Z0Offset
3. M500         ; Store setting to eeprom
4. M501         ; Set active parameters
5. M503         ; Display Active Parameters
6. G28 Z        ; Home Z Axis
7. G1 F60 Z0    ; Move nozzle to true 0 offset
8. M211 S0 - Switch off soft endstops
9. Move nozzle towards bed slowly until the paper can barely move
10. Take note of the Z on the printer display (take that number and add the measurment of the calibration sheet or device used)
11. M851 Z X.XX (X.XX being your z offset achieved)
12. M211 S1 - Enable Soft Endstops
13. M500 - Save settings to Eeprom
14. M501 - Set Active Parameters
15. M503 - display current settings