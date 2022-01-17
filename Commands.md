# Commands

## Startup

```
M502          ; Reset settings to configuration defaults...
M250 C135     ; Set contrast
M203 X250.00 Y250.00 Z5.00 E25.00
M201 X500.00 Y500.00 Z100.00 E1000.00
M92 X80.00 Y80.00 Z400.00 E108.9
M851 Z-3.0
M500          ; ...and Save to EEPROM. Use this on a new install.
M501          ; Read back in the saved EEPROM.
```

## Z-Offset

```
G28          ; Home
M851 Z0      ; Reset Z Offset
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
```


## Motion Configuration

```
M203 X150 Y150 Z5 E20
M201 X500 Y500 Z100 E1000
M204 P500 R1000 T1000
M205 J0.022
```

## UBL Bed Leveling

```
G29 P1        ; Do automated probing of the bed.
G29 T         ; View the Z compensation values.
G29 S1        ; Save UBL mesh points to EEPROM.
G29 F 10.0    ; Set Fade Height for correction at 10.0 mm.
G29 A         ; Activate the UBL System.
M500          ; Save current setup. WARNING - UBL will be active at power up, before any G28.


## Current

```
>>>M503
G21    ; Units in mm (mm)
M149 C ; Units in Celsius

# Filament settings: Disabled
M200 D1.75
M200 D0

# Steps per unit:
M92 X80.00 Y80.00 Z400.00 E108.9

# Maximum feedrates (units/s):
M203 X250.00 Y250.00 Z5.00 E25.00

# Maximum Acceleration (units/s2):
M201 X500.00 Y500.00 Z100.00 E1000.00

# Acceleration (units/s2): P<print_accel> R<retract_accel> T<travel_accel>
M204 P500.00 R500.00 T1000.00

# Advanced: B<min_segment_time_us> S<min_feedrate> T<min_travel_feedrate> J<junc_dev>
M205 B20000.00 S0.00 T0.00 J0.06

# Home offset:
M206 X0.00 Y0.00 Z0.00

# Unified Bed Leveling:
M420 S1 Z2.00

# Unified Bed Leveling System v1.01 active
# Active Mesh Slot: 1
# EEPROM can hold 16 meshes.
# Material heatup parameters:
M145 S0 H185 B45 F0
M145 S1 H240 B70 F0

# PID settings:
M301 P20.84 I1.96 D55.47

# LCD Contrast:
M250 C135

# Z-Probe Offset (mm):
M851 X-42.00 Y-4.00 Z-3.10

# Stepper driver current:
M906 X760 Y760 Z760
M906 T0 E900

# Hybrid Threshold:
M913 X100 Y100 Z3
M913 T0 E30

# Driver stepping mode:
M569 S1 X Y Z
M569 S1 T0 E

```





V85 stored settings retrieved (621 bytes; crc 14506)
Unified Bed Leveling System v1.01 active
Unified Bed Leveling initialized.

Mesh loaded from slot 1
Mesh 1 loaded from storage.
; Linear Units:
  G21 ; (mm)
; Temperature Units:
  M149 C ; Units in Celsius
; Filament settings (Disabled):
  M200 S0 D1.75
; Steps per unit:
  M92 X80.00 Y80.00 Z400.00 E97.72
; Max feedrates (units/s):
  M203 X150.00 Y150.00 Z12.00 E80.00
; Max Acceleration (units/s2):
  M201 X500.00 Y500.00 Z100.00 E1000.00
; Acceleration (units/s2) (P<print-accel> R<retract-accel> T<travel-accel>):
  M204 P500.00 R500.00 T500.00
; Advanced (B<min_segment_time_us> S<min_feedrate> T<min_travel_feedrate> X<max_x_jerk> Y<max_y_jerk> Z<max_z_jerk> E<max_e_jerk>):
  M205 B20000.00 S0.00 T0.00 X8.00 Y8.00 Z2.00 E10.00
; Home offset:
  M206 X0.00 Y0.00 Z0.00
; Unified Bed Leveling:
  M420 S1 Z1.00 ; Leveling ON

Unified Bed Leveling System v1.01 active
Active Mesh Slot 1
EEPROM can hold 16 meshes.

; Material heatup parameters:
  M145 S0 H185.00 B45.00 F0
  M145 S1 H240.00 B70.00 F0
; Hotend PID:
  M301 P23.55 I1.91 D72.69
; Bed PID:
  M304 P173.00 I35.00 D580.00
; LCD Contrast:
  M250 C135
; Z-Probe Offset:
  M851 X-42.00 Y-4.00 Z-3.00 ; (mm)
; Stepper driver current:
  M906 X760 Y760 Z760
  M906 T0 E900

; Hybrid Threshold:
  M913 X100 Y100 Z3
  M913 T0 E30

; Driver stepping mode:
  M569 S1 X Y Z
  M569 S1 T0 E
; Linear Advance:
  M900 K0.00