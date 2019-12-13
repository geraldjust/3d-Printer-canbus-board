# 3d-Printer-canbus-board
pcb board for 3d printer with canbus enabled


This project im looking into if its possible or if it should be done to add canbus. 
The first reason why i decided to design this that i plan to make a much larger printer and the print head would be very far from the main electronics. 
So i was thinking if canbus could be implemented. Ive worked with the atmega16m1 chips and i have made arduino addon to add support for it. I have a lot of experience with canbus systems and designing electronics for them. 
But im not to familiar with how Marlin calculates temperature PID etc.. So thats what i would need help with. I also need help in how to implement it on the main driver side. My theory is to make a simple canbus to serial brige for that end. But I would still need to implement a protocol to tranfer the data around. 

Future uses could also be the ability to have multi headed printers and each head is Can enabled. 
I will also try and make a board with a TMC2209 + the ATmega16m1 chip for stepper motors. But i would be worried if running at 1MBPS would be fast enough to be used in a system that is very time delicate. 

For this first prototype i made a 50mmx45mm board that has a 5v regulator, canbus transceiver, the atmega16m1(or 32m1 or 64m1), 5 IO , 1 high current mosfet lowside driver. Two mid current drivers (for fans) and two temperature inputs. I made it in a way that this could be used for either a extruder head, or connected to a heater bead.
