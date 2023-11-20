# Z80-computer

## Introduction
The Z80 is an 8-bit CPU designed by Zilog that was first introduced in 1976, and was one of the first microprocessors that allowed the general public, not just large businesses, to own a computer. The aim of this project is to design a Z80 computer with the following features: 256k of read only memory, and 256k of RAM, and output in the form of either 8 LEDs, or an LCD screen, the simplest possible way to load programs, and get some output from these programs.

## Components
### Z80
For the CPU I am using a Z80, this is because it is a fairly simple CPU to use, and has tons of resources online to learn how to use it, how to wire it up, and writing programs for it. The Z80 has been used in many popular products, such as TI calculators, the ZX spectrum, and inspired the CPUs for the Nintendo Gameboy. A0-14 are tied to the address bus, however A15 is used as the memory select flag, to select either the ROM or RAM to read from and write to, this means that memory addresses from 0000 to 7FFF are accessed from the ROM, while memory addresses from 8000 to FFFF are accessed from the RAM. 

### ROM
For the ROM I use an AT28c256, the address lines are tied to the address bus, and data lines to the databus. The CE (chip enable) pin is tied to the A15 pin on the Z80.
