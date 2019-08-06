# Saxilby bellringing simulator & Simbell wireless sensor
Here are some of the things that we learned from installing a bellringing simulator in our house. The setup is a Saxilby simulator, a Simbell wireless sensor, and Abel software on Windows 10 Home. The Saxilby is on the first floor and the rope runs through a hole in the floor to the hallway on the ground floor where we stand to ring.

## Connecting to the Saxilby wirelessly
As delivered, the Saxilby required a wired connection from its sensor to the computer on which we'd run the bellringing software ([Abel](http://www.abelsim.co.uk)). Because we installed the Saxilby upstairs in our home and we ring below it downstairs, we did not want to make another hole or a larger hole to accomodate the wire for the sensor, so we decided to go for a 3rd party wireless sensor. There are a few ways of making a wireless connection between a bell sensor and the ringing chamber, but we decided to go for a [Simbell Wireless transmitter/receiver](https://www.simbell.co.uk/index.htm).

The Simbell system consists of:
1. A reflective sticky strip to attach to the wheel of the Saxilby
2. A transmitter to attach to the frame of the Saxilby which contains a sensor that detects when the reflective strip moves past it. The transmitter gets power either from a battery pack or a DC power supply.
3. A receiver that attaches via USB to the computer running your bellringing software and receives the signals from the transmitter wirelessly. The receiver gets power over USB from the host computer.

## Making Saxilby & Simbell work together
The Simbell sensor is quite sensitive and, as delivered, detected not just the reflective strip, but also the edges of the metal bell-shaped weight that is attached to the Saxilby. To ensure good detection of only the reflective strip, we took the following steps:
1. Taped the edge of the Saxilby's bell weight with black tape all along the bottom
2. Taped a stiff piece of cardboard above the Simbell sensor to partially shield it from sunlight
3. Adjusted the sensitivity of the Simbell sensor so that it did not detect any seams in the tape, but still detected the reflective strip (Instructions: [SIMBELL SETUP - ADJUSTING TRANSMITTER SENSITIVITY](https://www.simbell.co.uk/video.htm))

When making changes and testing your setup, you can do some testing by moving the bell past the sensor with your hands, but before declaring victory, make sure to do some ringing so you can see how the sensor responds to the full range of motion at realistic speeds.

## Windows 10 S Mode, Simbell, and Abel
Bellringing using a simulator can be achieved with a cheap Windows 10 laptop running Abel and Simbell. But in order to install Abel software and the Simbell drivers, you need to switch your computer out of Windows 10 *S* or Windows 10 *in S Mode* (which is the same thing) if that's what it's running. You can switch Windows 10 out of S Mode without cost, so don't be afraid to buy a laptop with "Windows 10 S" as the operating system. Instructions: [How to switch out of S Mode](https://support.microsoft.com/en-gb/help/4456067/windows-10-switch-out-of-s-mode)

This [14" HP laptop from Argos](https://www.argos.co.uk/product/1403242) worked for us, although we had to reinstall the operating system from scratch to bust it out of S Mode because the Windows Store website wouldn't show the "Switch out of S Mode" page.

With Windows switched out of S Mode, the Simbell drivers were found and installed automatically by Windows 10. There was no need to install drivers manually from the Simbell site.

Windows 10 Home works fine with bellringing software. There's no need to buy Windows 10 Pro for this purpose. There does not appear to be any bellringing software for the Mac that works with external sensors, but it is possible to run Windows in a virtual machine on the Mac using software such as [Parallels](https://www.parallels.com/uk/).

Simbell and Abel support older versions of Windows too. If you use an older version of Windows, you may need to manually [download and install the drivers for Simbell](https://www.simbell.co.uk/software.htm).

## Simbell and All the Ports
Because we knew that we would be unplugging the Simbell receiver from the laptop so that it could be used for things other than bellringing, during setup we plugged the Simbell receiver into each USB port on the laptop in turn and used Device Manager to configure the settings to assign it to COM port 3. This way it won't matter which USB port the receiver is plugged into, there won't be any need to change software settings to get things to work.

The Simbell website has an instructional video ([SIMBELL TECHNICAL - SETTING / CHANGING THE COM PORT IN WINDOWS](https://www.simbell.co.uk/video.htm)) showing how to configure the COM port used by the receiver.

## Footpedal
The Saxilby was delivered to us with a wired USB footpedal with 3 switches. There was an accompanying mini-cd that possibly contained drivers and certainly contained a "data logger" (it literally had "PDF data logger" printed on it). Thinking it unwise to run any of the software on the included CD, we relied on Windows to recognise the pedal and install appropriate drivers. Windows recognised the device as a USB keyboard with each of the pedals mapped to "A", "B", and "C" keys. Abel provides some ability to configure keys for common functions. However, one of the most useful functions in Abel (which is mapped to the Escape key and calls Rounds, Stand, or just stops the ringing) did not appear have a customizable key binding. To work around this I used the Microsoft Keyboard Layout Creator to create a custom keyboard that mapped the A key (leftmost pedal) to the Escape key.

## Bellringing software in Windows in a Virtual Machine on the Mac
We were able to get ringing working on a real Windows laptop and on a virtual machine running in Parallels on a Mac. There was nothing particularly different about getting things working on a Mac. Parallels lets you choose whether physical devices like the Simbell receiver attach to the Windows guest operating system or the Mac host operating system. As long as you let the Windows guest operating system in the virtual machine see the hardware, it all works the same as on a physical Windows machine.
