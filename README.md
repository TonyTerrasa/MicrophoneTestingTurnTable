

## Turntable for Gathering Data About MEMS and Other Small Microphones

Designed by Tony Terrasa (Gabriel) under the direct supervision of David Ramsay in the MIT Media Lab. 


## Overview:

This is a physical tool that can be used to test microphones at any and all angles in one plane. It goes in tandem with a [Python library](https://github.com/dramsay9/pythonAudioMeasurements.git) for handling audio, collecting data, generating polar patterns for microphones, and interacting with the Arduino and stepper motors required for this build. Data collected with this tool allows one to understand the way a microphone reacts as a function of both angle and frequency, which can have a wide range of applications including but not limited to selective audio capture with microphone arrays. 


## Available Files:



*   STLs - contains STLs of all custom files for this project
*   Drawings - contains technical drawings for this project in both dwg and pdf format
*   SLDWKS - All of the original CAD files for this project
    *   All of these models are entirely parametric and dependent upon a dimensions.txt file. This file will be necessary in order to open and work with the project. 


## Parts:

Many parts for this turntable are of custom geometry and were 3D-printed for which a high-precision Form2 was used. While it is not necessary to 3D print the parts, the parts are designed with tolerances so that axles need to be sanded slightly to create a good push into their target slots. Whatever material they are made out of should be able to bear threads. 


### Purchasable online: 



*   [28BYJ-48 stepper motor](http://eeshop.unl.edu/pdf/Stepper+Driver.pdf)
*   [12-mm diameter slip ring](https://www.adafruit.com/product/1195)
*   [ULN2003 motor driver breakout board](https://www.aliexpress.com/item/5-pcs-ULN2003-Stepper-Motor-Driver-Board-Module/1923223718.html)
*   Male 0.1'' headers
*   9V power supply
*   Pogo pins (pad or through-whole)
*   3M-12 hex screws 
*   3M-30 hex screws
*   3M nuts


### Printables:



*   _Body_ - box-shaped frame onto which the whole system mounts
*   _BoardMount_ - mounting bracket that connects the _MountShaft _and the_ MountBoard_
*   _MountShaft_ - interacts with the _DrivenShaft_ and holds up the microphone boards
*   _DriveShaft_ - solid shaft with a gear, collar, and hole to interface with motor 
*   _DrivenShaft_ - hollow shaft with a gear and collar, driven by the _DriveShaft_
*   _MotorMount_ - mounts the motor to the body 
*   _SlipRingMount_ - mounts the slip ring to the body 


### Boards:



*   _Mount Board_ - PCB which connects the wires from within the table to the _MicBoard_
*   _MicBoard_ - custom PCB for the microphone that is to be tested


## Build 


### Necessary Assembly Tools:



*   Form 2 or other high-precision 3D printer
*   3M tap
*   Various grit sandpaper 
*   Hex screwdriver and small wrench for tightening fasteners


### Build Instructions:



1. Pre set-up
    1. Design, order, and build desired PCBs (see **Boards** sections)
    2. Print all parts and remove support material.
        1. When choosing the print orientations, keep in mind that the fit on most of the parts are designed such that sanding will be required to get them to fit snuggly. This was done to allow for supports to be used in the print and sanded back. That being said, avoid supports on areas of the parts that require many precise fits (gears) if possible. 
    3. Solder extensions onto 6 of the wires on the slip ring so that the wires can reach all the way through the _Shaft_ with about 1'' of extra clearance
    4. Tap all appropriate holes. All 2.5mm holes are meant to be tapped for 3M screws. 
2. Insert bearings into their designated holes in the top of the _Body_. The fit should be snug. Sand holes as necessary.
3. Mount Arduino and ULN2003 driver board to _Body _with 3M fasteners.
4. Mount motor and slip ring into _MotorMount_ and _SlipringMount_ respectively. Note that the motor is held to its mount with 2 tapped holes while the slip ring sits freely in its mount.
5. Mount the _MotorMount_ to the floor of the _Body_. The _MotorMount_ goes onto the set of 3 holes. Note that this mount is held to the body via tapped holes that enter through the floor of the body and into the bottom of the mount. 
6. Connect the motor to the output pins on the ULN2003 board, and use jumpers to connect the four input pins on the ULN2003 board with your desired pins on the Arduino. 
7. Insert the _DriveShaft_ and _DrivenShaft_ into their respective bearings. 
    5. The _DriveShaft_ goes with the motor. Make sure that the hole at the bottom engages with the shaft of the motor 
    6. The _DrivenShaft_ goes with the slip ring. Ensure that the gears mesh appropriately and there are no supports interfering with the rotation all the way around the gears. 
8. Fasten the _MountShaft_ to the _DrivenShaft_ with a 3M screw.
9. Feed the wires from the slip ring up through the _DrivenShaft_ and mount the _SlipringMount_ the the floor of the _Body_. Note this mounting mechanism is the same as for the _MotorMount_.
10. Ensure that all headers and pins are inserted into appropriate headers on _MountBoard_
11. Mount the _MountBoard_ onto the _BoardMount_ and with 3M fasteners around the perimeter.
12. Mount the _MicBoard_ to the _MountBoard _with the four designated holes, ensuring that appropriate pins and pads align. Note that the pogo pins should push against the screws and the screws should not be tightened too tight as to not break the pogo pins. 


## Boards:

This turntable is designed to allow for the mounting of any microphone that one can create a board for. The boards provided in the CAD are purely for reference for mounting holes for the design of the custom PCBs required for this turntable. The boards already used for data collection with this device were designed by David Ramsay will be posted in the future. See notes below about getting the best sound quality for more information about customizing boards.

The turntable is designed so that the _MountBoard_ stays in place at the top of the _Shaft_ and the _MicBoard_ can be customized for the desired microphone and mounted on top of the _MountBoard _ with spring-loaded pogo pins. The holes for the pogo pins are designed such that through-hole or pad pins can be used.Through-hole pins are used in the CAD. 


## Taking measurements


### Pre set-up

Before starting to take measurements, it is essential that the turntable is fully assembled. The following items will be necessary:



*   Turntable
*   Computer with companion Python library for this project and 2 USB-A ports
*   Audio interface
*   1 speaker
*   XLR cables 
    1. One to connect to the speaker
    2. One customized cable to connect to connect to end via jumpers
*   Lab power supply
*   9V power supply that terminals in female headers
*   USB-A to USB-B cable


### Taking measurement



1. Place the turntable and the speaker on two surfaces at least 6 feet away. It is important to make sure that the middle of the speaker is vertically level with where the microphone sits on the turntable.
2. Connect 9V power supply to the ULN2003 motor driver board. Ensure positive and negative ends are connected correctly. 
3. Connect computer to both the Arduino and audio interface with USB-A to USB-B cables.
4. Connect the microphone to the audio interface with the custom XLR cable, powering and grounding the microphone with the lab power supply. 
5. Connect computer to the audio interface and ensure that both audio can be received from the microphone and outputted to the speakers.
6. See the Python measurement script to ensure that your ports and Arduino are configured correctly. 
7. Run the measurement script.


## **Getting the best sound quality**:

In the first use of this device, several obstacles to good sound quality were encountered. Below is information on such issues and what was done to address them. 

_Grounding_ --  It was important to not ground signal from the microphone to the Arduino. The Arduino ground is not steady enough for high-quality signal reference. A lab power supply was instead used to power the microphone and ground the signal. 

_Amplification_ -- An Op-Amp circuit was incorporated into the _MicBoard_ design to amplify the incoming signal. 

_Balanced Audio_ -- The designed system does not inherently output balanced audio. In an attempt to reduce the noise from the signal, an auxiliary board was used to balance the signal before sending it to the computer. 

