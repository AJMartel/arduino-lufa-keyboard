Arduino LUFA Keyboard
=====================

A fork of Darran's Arduino UNO Keyboard HID firmware version 0.3 (http://hunt.net.nz/users/darran/weblog/b3029/Arduino_UNO_Keyboard_HID_version_03.html) which in turn is built on the wonderful LUFA (Lightweight USB Framework for AVRs) USB framework (http://www.fourwalledcubicle.com/LUFA.php). LUFA has undergone improvements since the last version of this library (0.3), so it no longer works with the latest versions of LUFA, so I took up this library to adapt it to the new LUFA as well as to allow it to be easily accessible to people who'd like to further contribute.

This library can be compiled into USB firmware that, when flashed onto an Arduino (UNO R3 for now), will make the Arduino report itself and behave as a USB keyboard.

To setup the project and upload the Arduino usbserial application firmware to an ATMEGA8U2 using the Arduino USB DFU bootloader:
1. unpack the source into LUFA's Projects directory
2. set ARDUINO_MODEL_PID in the makefile as appropriate
3. do "make clean; make"
4. put the 8U2 into USB DFU mode:
4.a. assert and hold the 8U2's RESET line
4.b. assert and hold the 8U2's HWB line
4.c. release the 8U2's RESET line
4.d. release the 8U2's HWB line
5. confirm that the board enumerates as either "Arduino Uno DFU" or "Arduino Mega 2560 DFU"
6. do "make dfu" (OS X or Linux - dfu-programmer must be installed first) or "make flip" (Windows - Flip must be installed first)
