# CH32M030C8T7-Dev-Board
A Dev Board to start using the CH32M030C8T6 MCU from WCH with 4 integrated half-bridge drivers and 2 usb PD connections

# Quad Half Bridge Possible Uses

## 2 Phase Stepper Motor Without Brake Resistor

## 3 Phase BLDC/PMSM Motor With Brake Resistor

### Brake Resistor
A low value brake resistor can be connected directly to the switching node of the half-bridge. 
This means the resistor dictates the highest current given the supply voltage. 

An inductor can also be combined with the brake resistor to act like a boost converter to allow for higher value brake resistors. 
Now the peak brake current is determined by the maximum voltage of the half-bridge and the gate-driver and the resistance of the brake resistor. 

## Power Converters
The circuit for the buck and boost converter are the same except for the input and output points. 
This allows the circuit to be used as a battery charger/discharger. 
Bucking into the battery and boosting out of it. 
### 4 Boost Converters
By connecting inductors to the switching node of each half-bridge they can be used as boost converters. 
The high side mosfets act as the output and the inductor as the input. 

### 4 Buck Converters
By connecting inductors to the switching node of each half-bridge like for the boost converts they can also be used as buck converters. 
The only difference is the input and output switch places. 
So for this implementation the high side fet is the input and the inductor is the output. 

### 2 Full Bridge Buck-Boost converters
By connecting an inductor between the switching nodes of 2 half-bridges, like an H-bridge, a full bridge buck-boost converter can be formed. 
This allows the high side mosfet of either half-bridge to be the input or the output. 
This means the circuit can be used for charging and discharging a battery while outputting a voltage above, below or equal to the battery voltage. 
