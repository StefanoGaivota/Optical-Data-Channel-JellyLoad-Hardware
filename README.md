Jelly Load is touted as the most inconvenient way of loading data into your 8 bit computer.
The concept is the collaborative creation of Dave Curran (Tynemouth Software) and Rod Hull (The Future Was 8 bit).

![Jelly-Load_Video-Excerpt](https://github.com/user-attachments/assets/b5859f96-f9bb-4654-9981-37c79c16dd64)

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
FreeCAD source is available for the mechanical elements (Optical Housing and Monitor Guide).

* Sensor array board:
![Sensor-array-board](https://github.com/StefanoGaivota/JellyLoad-Hardware/blob/main/JL_LDR-Sensor-Array/JL_LDR-Sensor-Array.jpg)
LDR (photoresistors) are arranged in the required matrix, connected from VCC to appropriate 14Way IDC header pins.
Sensor array board is fitted with Optical Housing mechanics to reduce ambient light interference and facilitate alignment on the receiving monitor.
Mechanical data is detailed later in this document.

* Signal Interface board:
![Signal-Interface-Board](https://github.com/StefanoGaivota/JellyLoad-Hardware/blob/main/JL_Signal-Interface/JL_Signal-Interface.jpg)
Sensor array signals are shunted by trim-pot resistors at the input to Schmitt inverters.
Switching threshold must be calibrated against known white-level with sensor array in place on receiving screen.
The appalling batch variability of photoresistors, (roughly 60% nominal resistance value at same light level),
required select-on-test trim-pots for each sensor to set switching thresholds at the Schmitt inverter input.
Kept surface mount components good and chunky (1206 and SOIC) for easier hand-assembly.

* Target Interface board:
![Target-Interface-Board](https://github.com/StefanoGaivota/JellyLoad-Hardware/blob/main/JellyLoad_Target-Interface_V2-0/JellyLoad_Target-Interface_V2-0.jpg)
Mostly just a connector interface to connect the 14Way IDC pins and route logic signals to User Port connector.
Solder blob config pads route the CLK signal to the user port pin required by the target computer.
This differs between PET, VIC20 and C64. Board profile is configured to fit inside a C64 cartridge case.
Case mechanics are shown on layer User.Eco1.  PDF of machining dimensions is made available for convenience.

* Optical Housing:
 
![Optical-Housing](https://github.com/StefanoGaivota/JellyLoad-Hardware/blob/main/JL_Mechanical-Data/Optical-Housing-Illustration.jpg)
The sensor array is fitted with the Optical Housing, as mentioned above, for the purpose of reducing ambient light interference and to help align with the optical channel.

* Monitor Guide:

![Monitor-Guide](https://github.com/StefanoGaivota/JellyLoad-Hardware/blob/main/JL_Mechanical-Data/Monitor-Guide-Illustration.jpg)
The Monitor Guide is attached to the receiving monitor screen, aligned with the appropriately scaled JellyLoad optical channel.
FreeCAD source is available for both these parts.  STL exports are also available for direct use in additive manufacturing processes.

Manufacturing Data in each board folder is most recent output from KiCAD and includes Bill-Of-Materials with Mouser stock codes, Gerber+Drill zip for PCB manufacture, component placement data and assembly drawing for the Signal Interface board and 3D view of sensor array board to show component arrangement.

JLC seemed fine with the Gerbers but don't generally hold stock of trimpots or LDRs, so I'm assuming that I'll need to get a knife and fork
onto this to assemble it myself.

A selection of JellyLoad encoded videos can be found here:
https://www.youtube.com/playlist?list=PLbE6E7xnjkkJwXpoj5DF8uXBsocBH2ZH-

Well, good luck!
