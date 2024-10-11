Jelly Load is touted as the most inconvenient way of loading data into your 8 bit computer.
The concept is the collaborative creation of Dave Curran (Tynemouth Software) and Rod Hull (The Future Was 8 bit).

My rough / ready understanding of how it works:
Data and clock signals are encoded into a video stream as a matrix of black or white areas.
The receiving interface senses the optical channel and converts the result into an 8 bit data word
for interpretation by the target computer upon receiving valid clock edge.

Take a look here:
https://www.tfw8b.com/introducing-jelly-load/
for a historical account.

This repository is my own effort at creating a JellyLoad receive interface for Commodore computer user port.

It comprises three separate boards for reasons of modularity and easier calibration.
Boards connect to each other via a 14way IDC cable assembly.
KiCAD source is available for schematic and PCB of each board.

* Sensor array board:
LDR (photoresistors) are arranged in the required matrix, connected from VCC to appropriate 14Way IDC header pins.

* Signal Interface board:
Sensor array signals are shunted by trim-pot resistors at the input to Schmitt inverters.
Switching threshold must be calibrated against known white-level with sensor array in place on receiving screen.
The appalling batch variability of photoresistors, (roughly 60% nominal resistance value at same light level),
required select-on-test trim-pots for each sensor to set switching thresholds at the Schmitt inverter input.
Kept surface mount components good and chunky (1206 and SOIC) for easier hand-assembly.

* Target Interface board:
Mostly just a connector interface to connect the 14Way IDC pins and route logic signals to User Port connector.
Solder blob config pads route the CLK signal to the user port pin required by the target computer.
This differs between PET, VIC20 and C64. Board profile is configured to fit inside a C64 cartridge case.
Case mechanics are shown on layer User.Eco1.  PDF of machining dimensions is made available for convenience.

Manufacturing Data in each folder is most recent output from KiCAD and includes Bill-Of-Materials with Mouser stock codes, Gerber+Drill zip for PCB manufacture, component placement data and assembly drawing for the Signal Interface board and 3D view of sensor array board to show component arrangement.

JLC seemed fine with the Gerbers but don't generally hold stock of trimpots or LDRs, so I'm assuming that I'll need to get a knife and fork
onto this to assemble it myself.

A selection of JellyLoad encoded videos can be found here:
https://www.youtube.com/playlist?list=PLbE6E7xnjkkJwXpoj5DF8uXBsocBH2ZH-

Well, good luck!
