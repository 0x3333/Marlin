Startup
=======

M502          ; Reset settings to configuration defaults...
M250 C135     ; Set contrast
;M851 Z-3.1    ; Reset Z0Offset
M500          ; ...and Save to EEPROM. Use this on a new install.
M501          ; Read back in the saved EEPROM.


Z-Offset
========

G28          ; Home
M851 Z0      ; Reset Z0Offset
M500         ; Store setting to eeprom
M501         ; Set active parameters
M503         ; Display Active Parameters
G28 Z        ; Home Z Axis
G1 F60 Z0    ; Move nozzle to true 0 offset
M211 S0      ; Switch off soft endstops
             ; Move nozzle towards bed slowly until the paper can barely move
             ; Take note of the Z on the printer display (take that number and add the measurment of the calibration sheet or device used)
M851 Z X.XX  ; (X.XX being your z offset achieved)
M211 S1      ; Enable Soft Endstops
M500         ; Save settings to Eeprom
M501         ; Set Active Parameters
M503         ; display current settings


UBL Bed Leveling
================

G29 P1        ; Do automated probing of the bed.
G29 T         ; View the Z compensation values.
G29 S1        ; Save UBL mesh points to EEPROM.
G29 F 10.0    ; Set Fade Height for correction at 10.0 mm.
G29 A         ; Activate the UBL System.
M500          ; Save current setup. WARNING - UBL will be active at power up, before any G28.
