# Z80-computer

The Z80 is an 8-bit CPU designed by Zilog that was first introduced in 1976, and was one of the first microprocessors that allowed the general public, not just large businesses, to own a computer. The aim of this project is to design a Z80 computer with the following features: 256k of read only memory, and 256k of RAM, and output in the form of either 8 LEDs, or an LCD screen, the simplest possible way to load programs, and get some output from these programs. I hope to explain the design process and all the moving parts in this document. 

## Components
### The Big Three
- Zilog CPU. I am using a modern Z84C00. Its static design means that the clock signal can be as slow or as fast as we want (up to several MHz).
- AT28c256. A 256k EEPROM. Or more specifically, it can contain 32k words, each containing 8 bits. I will be using as the ROM where the instructions for the program is held.
- CY62256NLL-70PXC. A 256k SRAM. Yet again, its really 32k, each containing 8 bits of data.
### Power. 
> The computer can be powered by either using an external power supply, or by plugging in the Arduino.
- LM7805. A 5V linear regulator.
### Clock pulse
- NE555 timer. This will be used as the timer.
- 10nf to 100nf capacitor.
- 1M trim pot, to adjust the clock rate.
### Output
- A generic LCD display.
### Input
- A PS/2 port that a keyboard can be plugged into,
- Arduino Nano. Used to take input from the keyboard, and turn it into a suitable ASCII character.
- 74HC595. A shift register that will be used to send data from the Arduino, to the data bus.
### Logic
- 74x04 chip. A NOT gate. This will be used to turn high signals low, and low signals high. 
- 74x32 chip. An OR gate. This will be used to output a high signal when either of the inputs are high. Useful for outputting an active low signal, depending on two active low inputs.
### Miscellaneous
- A momentary push button. This will be used as our reset button.
- Some 100n capacitors to help clean out the voltage throughout the circuit.
- Some way to write data to an EEPROM. I am using an XGecuPro T48.
