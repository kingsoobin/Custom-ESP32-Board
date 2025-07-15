# Custom-ESP32-Board

## Introduction
This is where I keep all my files and progress for my custom ESP32 board design and assembly on Altium Designer. 

## Log
1. Find the ESP32-S3-DevKitM-1 manual on EspressIF's DevKits. Downloaded manual and schematic for the MINI-1
2. Identify components in schematic and find in Digikey. Find the manufactuer's product number to search for components on LCSC Electronics. Check availability before importing Digikey Part Number for component information into Altium's Manufacturer's Part Search
3. Create new component in SCH Library and import LCSC part number. Create component.
4. Import components into main schematic and refer to EspressIF's schematic to make connections
5. Both created own components and also imported downloaded components
6. Learned that for important pins, I can use two 27 resistors to improve signal quality and also if debugging needs to be done later that requires this pin to be disconnected, I can simply remove these resistors
7. Original schematic is using microUSB, but I want to use USB-C -> went to 99Tech to search for boards that use USB-C to look at schematic to see how to connect for my board 
