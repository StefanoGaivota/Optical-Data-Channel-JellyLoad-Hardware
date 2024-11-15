Jelly Load is touted as one of the most inconvenient ways of loading data into your 8 bit computer.<br>
The concept is the collaborative creation of Dave Curran (Tynemouth Software) and Rod Hull (The Future Was 8 bit).

![Jelly-Load_Video-Excerpt](https://github.com/user-attachments/assets/b5859f96-f9bb-4654-9981-37c79c16dd64)

My rough / ready understanding of how it works:<br>
Data and clock signals are encoded into a video stream as a matrix of black or white areas.<br>
The receiving interface senses the optical channel and converts the result into an 8 bit data word
for interpretation by the target computer upon receiving valid clock edge.

Take a look here:<br>
https://www.tfw8b.com/introducing-jelly-load/<br>
for a historical account.

The loader binaries for VIC20 can be found here:<br>
https://www.tfw8b.com/wp-content/uploads/2024/09/JellyLoad-VIC20-240908.zip<br>
(different ones depending upon your RAM configuration)

This repository is my own effort at creating a JellyLoad receive interface for Commodore computer user port.

It comprises two separate boards which connect to each other via a 14way IDC cable assembly along with associated opto-mechanical components.<br>
KiCAD source is available for schematic and PCB of each board.<br>
FreeCAD source is available for the mechanical elements (Optical Housing and Monitor Guide).<br>
Manufacturing data generated from these sources is detailed later in this document.<br><br>

* Optical Interface board:
![Sensor-array-board](https://github.com/StefanoGaivota/Optical-Data-Channel-JellyLoad-Hardware/blob/main/JellyLoad-Combi_V2-0/JellyLoad-Combi_V2-0.jpg)
Phototransistors are arranged in the required matrix, photocurrent converted to voltage at input of Schmitt inverter. Inverter outputs are routed to 14 Way IDC.
Clock signal sensor is indicated by and LED underneath the IDC connector.
<br><br>

* Target Interface board:
![Target-Interface-Board](https://github.com/StefanoGaivota/JellyLoad-Hardware/blob/main/JellyLoad_Target-Interface_V2-0/JellyLoad_Target-Interface_V2-0.jpg)
Target interface connects the 14Way IDC pins and routes logic signals to target computer User Port connector.<br>
Solder blob config pads route the CLK signal to the user port pin required by the target computer.<br>
This differs between PET, VIC20 and C64. Blob your required option.<br>
Board profile is configured to fit inside a C64 cartridge case.<br>
Case mechanics are shown on layer User.Eco1.<br>
PDF of machining dimensions is made available for convenience.<br><br>

* Optical Housing:
 
![Optical-Housing](https://github.com/StefanoGaivota/JellyLoad-Hardware/blob/main/JL_Mechanical-Data/Optical-Housing-Illustration.jpg)

The Optical Interface board is fitted with this Optical Housing for the purpose of reducing ambient light interference and to help align with the optical channel.<br>
Optical aperture adaptors (glass spheres) are accommodated in this section to match the sensor aperture to the available width. A specification for suitable spheres is available in the mechanical data directory along with an illustration of the optical aperture translation.<br>
The housing can be secured to the board with adhesive (e.g. cyanoacrylate) or careful heat-staking of the retaining lugs.<br><br>

* Monitor Guide:

![Monitor-Guide](https://github.com/StefanoGaivota/JellyLoad-Hardware/blob/main/JL_Mechanical-Data/Monitor-Guide-Illustration.jpg)

The Monitor Guide is attached to the receiving monitor screen, aligned with the appropriately scaled JellyLoad optical channel.<br><br>

* Manufacturing Data:<br>

Manufacturing Data in each board folder is the most recent output from KiCAD.<br>
Bill-Of-Materials (BOM) with Mouser stock codes. BOM and pick/place files for use with JLC.<br>
Gerber+Drill zip for PCB manufacture.<br>

Assembly tooling holes are 1.152mm top-left and bottom right of layout. Specify "Tooling holes added by customer" at assembly stage.<br><br>

STL exports of Optical Housing and Monitor Guide can be used with most additive manufacturing processes.<br><br>

A selection of JellyLoad encoded videos can be found here:<br>
https://www.youtube.com/playlist?list=PLbE6E7xnjkkJwXpoj5DF8uXBsocBH2ZH-

Well, good luck!
