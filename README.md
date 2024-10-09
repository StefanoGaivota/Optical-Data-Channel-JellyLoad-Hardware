Jelly Load is touted as the most inconvenient way of loading data into your 8 bit computer.
Data and clock signals are encoded into a video stream as a matrix of black or white areas.
The receiving interface senses the optical channel and converts the result into an 8 bit data word
for interpretation by the target computer.

This repository is my own effort at creating a JellyLoad receive interface for Commodore computer user port.

It comprises three separate boards for reasons of modularity and easier calibration.
Each board connects via a 14way IDC cable.

* Sensor array board:
LDR (photoresistors) are arranged in the required matrix.

* Signal Interface board:
Sensor matrix signals are shunted by trim-pot resistors at the input to Schmitt inverters.
Switching threshold must be calibrated against known white-level with sensor matrix in place on receiving screen.
The appalling batch variability of photoresistors, (roughly 60% nominal resistance value at same light level),
required select-on-test trim-pots for each sensor to set switching thresholds at the Schmitt inverter input.
Kept surface mount components good and chunky (1206 and SOIC) for easier hand-assembly.

* Target Interface board:
Mostly just a connector interface.  Solder blob config pads route the CLK signal to the user port pin required by the
target computer.  This differs between PET, VIC20 and C64. Board profile is configured to fit inside a C64 cartridge case.

KiCAD source is available for both schematic and PCB of each board.

Manufacturing Data is most recent output from KiCAD and includes Bill-Of-Materials with Mouser stock codes, Gerber+Drill zip for PCB manufacture,
component placement data and assembly drawing for the Signal Interface board and 3D view of sensor array board to show component arrangement.

JLC seemed fine with the Gerbers but don't generally hold stock of trimpots or LDRs, so I'm assuming that I'll need to get a knife and fork
onto this to assemble it myself.

Well, good luck!
