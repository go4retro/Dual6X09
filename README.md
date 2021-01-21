# Dual 6X09E Adapter Schematic and Printed Circuit Board
This PCB will allow the use of two different 6X09E variants in a 6809E-based system.  Only one CPU can be active at any time, and the CPU must be selected before boot.

## Technical Details

The Motorola MC6809E and the Hitachi 63C09E microprocessors both support tristating most of their I/O pins as a way to support a multi-processor environment.  The TSC (Tri State Control) line, when high, places most CPU I/O lines in a high impedence (Hi-Z) state, where they can be safely connected to other output lines.  The address, data, and read/write lines are tristated when TSC is set to logical 1 (5volt). Other lines, like E, Q, the various interrupt lines, and RESET are all inputs, which means they can always be connected together.

This is enough to support running two CPUs in a Tandy Color computer.  However, some aftermarket devices that reside in the CPU socket require access to additional output lines on the CPU that are not tri-stated (LIC, AVMA, BUSY, BA, and BS).  These lines tell the rest of the circuit the internal state of the CPU, so it makes sense they are always active.  Thus, these lines must be tri-stated using external components so the relevant signal from the currently active CPU will be sent to the CPU socket. If these signals are not needed, the external circuitry can be simply omitted.

## Purchase
You can purchase this PCB at http://store.go4retro.com/dual-6x09-pcb/

## License
Copyright (C) 2017-20  Jim Brain, RETRO Innovations

These files are free designs; you can redistribute them and/or modify
them under the terms of the Creative Commons Attribution-ShareAlike 
4.0 International License.

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-sa/4.0/>.

These files are distributed in the hope that they will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
license for more details.

