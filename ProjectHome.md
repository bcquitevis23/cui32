The CUI32 is a new version of the [CREATE USB Interface](http://www.create.ucsb.edu/~dano/CUI/), based on a 32-bit PIC microcontroller.
The CUI32 homepage, forum, and community blog is here:  http://www.overtone-labs.com/
and you can buy a CUI32 board for $39.95 (less in quantity) here:

[http://www.sparkfun.com/commerce/product\_info.php?products\_id=9645](http://www.sparkfun.com/commerce/product_info.php?products_id=9645)

The board can be powered by USB, or by a battery / external supply, and the prototyping section of the board can be broken-off in order to make the size smaller if desired.

The CUI32 ships with "StickOS" installed as its default firmware - this is an full operating system created by Rich Testardi with an on-board BASIC compiler, line editor, debugger, profiler, and simple file system to create new firmware programs, save them and run them, all without having to install any software on your host computer. The only thing that's needed is a standard terminal emulator (Hyperterminal or Teraterm on windows, the "screen" terminal command in Mac OS X, etc.).  StickOS is a very elegant approach for beginners, with a built-in help system - and also works great as a quick prototyping environment for advanced users. You can see some examples on the [StickOS website](http://cpustick.com/) or [YouTube](http://www.youtube.com/watch?v=nSgha8qjB3E).  Don't miss the [StickOS User's Guide](http://cpustick.com/stickos.htm).

The CUI32 also ships with a standard bootloader pre-installed, so you don't need a PIC programmer to write your own C programs that take full advantage of the powerful 32-bit PIC!  All of Microchip's own examples from their USB framework ( http://www.microchip.com/usb/ ) can of course be compiled for the CUI32 - things like HID mouse/keyboard/game controller devices, USB-MIDI and USB-Audio devices, etc. While these are more complex than a BASIC program written in StickOS, the CUI32 homepage and this Google Code repository / documentation wiki will allow anyone to share more advanced examples that are set up specifically for the CUI32 as well.

There is a footprint on the bottom of the CUI32 for a female USB connector that allows you to connect a device to the board when you program it for USB-host mode. Note that StickOS includes a FAT32 file system and supports logging data to a standard flash drive, or you can program the CUI32 to be a host for whatever you want. Since the CUI32 uses the same family of PIC32s as the UBW32 board (homepage: http://www.schmalzhaus.com/UBW32/ ), it is compatible with a lot of the resources that have already been developed in this similar open source project, such as the UBW32 firmware, and this bootloader application that works on Mac OS X and Linux:  http://www.paintyourdragon.com/uc/ubw32/index.html

The layout of the 16 analog input pins on the CUI32 puts them in triplets - each with its own V+ and GND, and users can choose whether the V+ pins should provide 3.3V / 5V via a selector on the board.  Since the CUI32's A-to-D converter runs at 0-3.3V, this selector should usually be set to the 3.3V position for capturing sensor data, but these analog input pins can also be turned into outputs in the firmware - making them useful to control things like servos, etc.  In this case, choosing the 5V setting for V+ allows you to fully power any servo motors, which can plug directly into the board (if you put on standard 0.1" header pins) since the triplet pin-order matches that of servo connectors. All of the pins of the PIC32 are available on the board, and many of them are 5V-tolerant (as indicated on the silkscreen) when used as digital inputs.


[http://cui32.googlecode.com/files/CUI32profile.JPG](http://www.overtone-labs.com/)