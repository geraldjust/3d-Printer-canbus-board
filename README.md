# 3d-Printer-canbus-board
pcb board for 3d printer with canbus enabled


This project im looking into if its possible or if it should be done to add canbus. 
The first reason why i decided to design this that i plan to make a much larger printer and the print head would be very far from the main electronics. 
So i was thinking if canbus could be implemented. I have a lot of experience with canbus systems and designing electronics for them. 
But im not to familiar with how Marlin calculates temperature PID etc.. So thats what i would need help with. I also need help in how to implement it on the main driver side. My theory is to make a simple canbus to serial brige for that end. But I would still need to implement a protocol to tranfer the data around. 

Future uses could also be the ability to have multi headed printers and each head is Can enabled. 
I will also try and make a board with a TMC2209 + STM32 chip for stepper motors. But i would be worried if running at 1MBPS would be fast enough to be used in a system that is very time delicate. Prehaps Using the TMC2209 iva UART mode to a serial to can board. 

For this first prototype i made a 25mmx45mm board that has a 3.3v regulator, canbus transceiver, a STM32 chip (Varieties will be available), 1 high current mosfet lowside driver (for hotend). Two mid current drivers (for fans) and 1 temperature input (4.7k pullup). Currently it also has a limit switch footprint as for the Core XY printer that im designing this for has the limit switch for Y on the print head. Future i can try and add another connector for bed leveling or other things. 

This first version of the head will be Will be available with different packages that can be interchangeable with various product lines of STM32 chips.

As for code it wont be avaiable just let. Currently having these boards made and a companion board that will act in a "dumb" mode. were it will interface via IO pins. For example, limit switch gets send though canbus, then on the board attached to the main board turn that canbus packet into IO digital signals. For the thermistor i will be using the PT100 type of table on marlin side. And the reciver board will be using a DAC to then send out a 0-3.3v analog singal. The switching on/off of the heater cartrage will be also send though canbus. Alot of this will be theoretical. But hopefully in the future, when or if malrin supports canbus, we will be able to implement the PID control on the head itself and just be able to send a command (similar to g code or something like that though canbus) and the head then control it locally. 

I feel this will be super useful for multi head or tool changers in the future. 


