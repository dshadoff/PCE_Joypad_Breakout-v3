# PCE_Joypad_Breakout-v3

This project was made in the EAGLE PC Board design packagei (free version),
to assist in the development and experimentation of new joypad devices for
the PC Engine videogame system.

Features include:
- a prototype-style area for mounting projects
- 3.3V regulator and level-shift logic for alternate inputs
- 5V inputs for pass-through and switched operation, as a Memory Base 128
would do

This project also includes the Gerber files, which you can download and
send to your favorite PC Board fabrication company, to make some for
yourself.


# Important:

Do not place a heavy load on this device,  especially if your console has
been modified in any way, as the power supply may already have a higher load
on it than intended.  This device draws power from the PC Engine's joypad
port, which has limited power available. Overloading this circuit may cause
irreparable damage to the PC Engine unit.  I cannot be held responsible for
damage caused for this (or any other) reason.

You should only use this board if you:
a) Understand what it does, and know the impacts of using it with your
protoype, and
b) Understand and accept the risks of using it.

Loads required by average, licensed devices (for reference):
Joypad: approx. 1 mA
PCE Mouse: approx. 6 mA
Memory Base 128: approx 15 mA


# Notes:

The header at the top of the board is the same pinout as that on the inside
of a PC Engine joypad (where the cable meets the board). If you can find a
compatible replacement cable (such as at a website like Console5.com), such
a cable should work... however, be careful about orientation: the "GND"
wire at the end of the pin header shouls connect with the round metal
portion of the mini-DIN plug.

The header immediately adjacent is 5V-logic outputs, feeding to the PCE.

The header adjacent to the mini-DIN jack is for measuring the data back
from the connected peripheral (note: depending on the swithcing logic,
this may or may not be the data fed back to the PCE).

The jumper at the bottom-right of the board can be placed in one of
three positions, to determine which input is sent to the PC Engine:
- bottom position (center bridged with bottom): always send input from
the 5V joypad connector
- top position (center bridged with top): always send input from the
3.3V connector on the right (prototype)
- middle position (center-left bridged with center-right): switch based
on 3.3V value from the pin at the very bottom of the right-hand header
(separated slightly from the main group of pins).
OR, if you would like to drive the selector from 5V logic, do not jumper,
and attach the 5V signal to the center-left pin.
LOW = PC Engine mini-DIN input
HIGH = 3.3V mini-DIN input

The two jumpers within the 3.3V bock (at D1 and D3) bring those inputs
to ground, and are useful if emulating the MB128 peripheral.


# Errata:

This board lacks pullup resistors on the D0-D3 lines on both the
5V inputs and the 3.3V inputs.  This could be a problem if that input
is 'active' while on input is connected - random data will appear for
those bits.  (This will eb fixed in a subsequent version).

