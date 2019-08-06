# Saxilby bellringing simulator & Simbell wireless sensor

The Saxilby ringing simulator comes with a (magnetic?) position sensor .
The sensor is wired with a short cable that has an AV end, and there's a long AV-to-serial cable, and a serial-to-USB cable.
The sensor data needs to make its way to the ringing software on the computer so, as supplied, there needs to be a route for the sensor wiring to run from the Saxilby wheel to the computer.

The Saxilby manufacturer does not provide a wireless sensor option. However, it should be possible to pass sensor data wirelessly. There are at least two options:

1. Wireless serial adaptor

This option uses the existing sensor, but adds a wireless adapter to send the data to the computer over wifi.

2. SIMBELL wireless ringing sensors

This option does not use the existing sensor. Instead the Saxilby would have a reflector stuck to the bell and a wireless SIMBELL transmitter would be attached to the frame, while the computer would be plugged into a wireless SIMBELL receiver.

We went with the SIMBELL option connected to a Mac running Windows in a Parallels VM with Beltower ringing software.

## Setting up Saxilby and SIMBELL

1. Attach the reflector to the Saxilby: we attached the reflector to the Saxilby on the left edge of the wheel with the bottom of the reflector aligned with the bolt, so just slightly above half way vertically.
2. Attach the transmitter to the Saxilby: lie the box on the frame facing the reflector and attach with something appropriate
3. Connect the receiver to the computer:
a) Plug the receiver into the USB port
b) Direct the USB device to connect to the virtual machine in Parallels
c) In Windows 7, we had to download the drivers from the SIMBELL website; otherwise let Windows install the drivers automatically
d) Open Device Manager and see which COM port has been assigned (in our case, `COM3`)
e) In Beltower: `Settings | Sensors...` > Set `Input Mode` to `Serial Interface` and set the `Input` to `COM3` or whatever port you saw in Device Manager
f) In Beltower: `Options | Ring Options...` set `Bell Sensors` to `1` or the number of your bell sensor
g) Turn on the transmitter!

You should now be able to hear your bell ring in Beltower when the reflector on the Saxilby moves past the sensor.

## Making Saxilby & Simbell work together
The Simbell sensor is quite sensitive and, as delivered, will probably detect not just the reflective strip, but also the edges of the metal bell-shaped weight that is attached to the Saxilby. To ensure good detection of only the reflective strip, we recommend the following steps:
1. Tape the edge of the bell weight with black tape all along the bottom
2. If your simulator is in normal lighting conditions, attach a piece of cardboard above the sensor to partially shield it from sunlight
3. Adjust the sensitivity of the sensor so that it does not detect any seams in the tape, but still detects the reflective strip (Instructions: [SIMBELL SETUP - ADJUSTING TRANSMITTER SENSITIVITY](https://www.simbell.co.uk/video.htm))

When making changes and testing your setup, you can do some testing by moving the bell past the sensor with your hands, but before declaring victory, make sure to do some ringing so you can see how the sensor responds to the full range of motion at realistic speeds.

## Windows 10 S Mode, Simbell, and Abel
Bellringing using a simulator can be achieved with a cheap Windows 10 laptop running Abel and Simbell. But in order to install Abel software and the Simbell drivers, you need to make sure that your laptop is not running Windows 10 *S* or Windows 10 *in S Mode* (which is the same thing). You can switch Windows 10 out of S Mode without cost, so don't be afraid to buy a laptop with "Windows 10 S". Windows 10 Home works fine. Instructions: [How to switch out of S Mode](https://support.microsoft.com/en-gb/help/4456067/windows-10-switch-out-of-s-mode)
