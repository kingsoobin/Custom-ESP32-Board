# Custom-ESP32-Board

## Introduction
This is where I keep all my files and progress for my custom ESP32 board design and assembly on Altium Designer. 

## Log
### Schematic Library & Schematic Connection
1. Find the ESP32-S3-DevKitM-1 manual on EspressIF's DevKits. Downloaded manual and schematic for the MINI-1
2. Identify components in schematic and find in Digikey. Find the manufactuer's product number to search for components on LCSC Electronics. Check availability before importing Digikey Part Number for component information into Altium's Manufacturer's Part Search
3. Create new component in SCH Library and import LCSC part number. Create component.
4. Import components into main schematic and refer to EspressIF's schematic to make connections
5. Both created own components and also imported downloaded components
6. Learned that for important pins, I can use two 27 resistors to improve signal quality and also if debugging needs to be done later that requires this pin to be disconnected, I can simply remove these resistors
7. Original schematic is using microUSB, but I want to use USB-C -> went to 99Tech to search for boards that use USB-C to look at schematic to see how to connect for my board -> find MOLEX USB-C connector
8. Assemble PCB schematic for USB-C based on 99Tech's schematic
9. Learned that I can use a jumper instead of diode. Used jumper to connect 5V of USB connectors 1 and 2 to 5V source
10. Learned about TVS Diodes used as protection.
11. Created a 5V to 3.3V converter using a regulator. IC -> Power Management -> Voltage Regulators (Low drop out regulators)
12. Read datasheet of regulator to see how it needs to be connected. In this case, it was recommended for 10uF capacitor on output with ESR no more than 3 ohms. It also uses 10uF capacitor in INPUT, but looking at the USB 2.0 specification max capacitance on power, 10uF is the recommended max. So opted to look for smallest possible in the datasheet (1uF to 10uF).
13. Created component that handles USB Connector to Serial Port
### Footprints
14. Download and import .SchLib and .step files from Digikey and/or SnapEDA and/or 3DContentCentral for standard components: ie. resistor, capacitor
15. Read drawing for more complex components (ie. headers) to create own footprint on Footprint Wizard in Altium (Dual In-line Packages): input hole dimensions
16. referred to jlcPCB capabilities to see what is the smallest text I can put on the pcb when labeling
17. Created SMD component footprint (diode)
18. For all the components that needed a footprint created, I went to its datasheet and looked for the Recommended Solder Pad Footprint for dimensions to create footprint on Footprint Wizard
19. Download footprint to all components in sch library and update schematic.
### Board Creation
20. Go back to schematic sheet for esp32 dev kit to see board dimensions
21. Place main components first before arranging the smaller one. I used the Sequentially Reposition Selected Components tool to stay organized and efficient.
### Board Connections
22. Went to jlcPCB capabilities sheet again to look at the minimum trace width and spacing, minv via hole size, solder mask expansion to set the rules.
23. Made rules to override component clearance for the 0OHM pairs
