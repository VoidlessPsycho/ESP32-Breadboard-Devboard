# ESP32 Breadboard Devboard Journal

**Total number of entries: 5** \
**Total hours spent: 20 hours**

### June 28, 2026: Created Schematic
Today, I wanted to make an ESP32 Devboard. I had previously had problems with ESP32 because all the modules I found were too wide to fit on a breadboard. This is why I decided to embark on creating my own ESP32 devboard that would fit on a breadboard.

First, I selected which ESP32 microcontroller I wanted to use as the core of my project. There were many different types, such as the ESP32-S3 and -C3. I decided on using the ESP32-S3-WROOM-1 Module because it had a good balance of most features and less complexity. I used Gemini/ChatGPT for advice and also looked through an Instructables guide and the EspressIF documentation and hardware references.

![Schematic](https://cdn.hackclub.com/019f11c9-58b1-7402-88db-9462aecc459a/paste-1782709835237.png)

I started with the WROOM module in the center. 

**USB/LDO:** \
Then, I added the USB-C receptacle, the 14-pin one as it worked for USB 2.0 and had a simplified schematic to make it easier to route everything. I first used the AP2112K-3.3TRG1 low-dropout regulator to convert the 5v from the USB to 3.3v that the ESP32 runs on. \
However, I later realized that I also want to have a input power header pin, that can have up to 12v of input voltage. To accomplish this, I switched from the AP2112 to the SGM2212-3.3XKC3G in the ESP32-S3-DevKitC schematic. I also added capacitors around this LDO and also a resistor coming out of it into an LED as a power-on indicator. 

**Power:** \
I also had to add decoupling capacitors around the 3.3v pin on the ESP32 to smooth out power oscillations. I used the hardware references to understand which capacitors to include. 

**Buttons:** \
I decided to include BOOT/RESET buttons as they were included in my current ESP32 module. I wanted to add these just in case right now so I could use them in my module if the need arised. \
While reviewing my schematic and the hardware reference, I realized I left the GPIO0 (Boot) and CHIP_PU pins floating. After checking the hardware peripheral guidelines, I connected the buttons to the 3v3 line. 

**Header Pins:** \
I labeled the header pins in the order that would make it easiest to make a PCB. \
<img src="https://cdn.hackclub.com/019f11cf-508f-7e82-8a94-10815438a004/paste-1782710226259.png" alt="Header Pin Wiring Explanation" style="max-height:500"> \
Basically, since my ESP32 module was gonna be above all the header pins (as putting it in between would make it too wide for the breadboard), I wanted to make it so that the PCB traces from the header pins to the ESP32 pins wouldn't be overlapping too much. The incomplete illustration above kind of shows my thought process with how I was gonna make the traces and which ESP32 pins went where on the header pin connector. 

This is how I designed my schematic for my ESP32 board that I want to be able to fit on a breadboard.

**Time spent this session: 5 hours**
<hr>

### June 28 P2: Footprint Assignment and Beginning PCB Design
After completing the schematic, I began with assigning footprints to all my symbols. \
<img src="https://cdn.hackclub.com/019f149a-1e43-735c-adf0-e72ce1f2a6a1/paste-1782757071560.png" alt="Assign Footprints" style="max-width:500"> \
The 10uF capacitor and led have a 0603 footprint, and the remaining capacitors, fuses, resistors have a 0402 footprint. I used the easyeda2kicad script to get footprints for buttons, the wroom module, ldo, and usb-c receptacle. I did a lot of research on which footprints to use for which components, and also measured my current devboards to see what they use. 

I then began designing my PCB. \
<img src="https://cdn.hackclub.com/019f149c-9d80-7a14-90fc-fcfe5756405d/paste-1782757234975.png" alt="PCB" style="max-height:500px"> \
I made it so the wroom module and USB are on opposite ends of the PCB. The height of the pcb is the height of the header pins + the height of the wroom module except for the antenna, which hangs over the edge. \
The components near the USB-C receptacle are the LED, USB ESD, LDO, Fuse, Diode, etc. All things that make sure the power doesn't blow up the chip. 

I also began adding some of the traces for the header pins but then decided to wait until all the other important things were done.

**Time spent this session: 2 hours**
<hr>

### June 29: Finishing PCB Design
Today I finished designing the PCB.

<img src="https://cdn.hackclub.com/019f19c6-0239-7bc1-84a9-02b9754b46d2/paste-1782843834245.png" alt="PCB" style="max-height:500px">

First, I made sure all the components near the USB-C receptacle were connected. This included resistors, decoupling capacitors, ESD and LDO for power, etc.

I then worked on the decoupling capacitors and resistors near the main microcontroller, which I had to put on the back side because there was no space on the front side near the pads. 

I also had to use differential routing to route the USB data traces, and had to use vias to switch the sides of the data traces halfway through because of the location of their respective pads on the microcontroller. 

After this, I routed all the header pins, making sure to keep them as compact as possible.

I then routed the buttons, the BOOT (GPIO0) and EN (CHIP_PU) buttons, having to move around the header pin traces to be able to route them properly.

Afterwards, I routed the 3.3v and 5v traces to the microcontroller, header pins, and other components. 

After routing all the components, I had to use a ground plane fill to connect all the grounds. Some of the header pin grounds near the top weren't able to connect because of the density of the header pin traces. So I had to move up all the header pins on the right side to make space for a GND pin on top. 

After checking DRC, I edited some of the footprints to eliminate bogus errors. I also had to use vias and traces to connect all the GND pads to the ground fill. 

I fixed up the silkscreen by removing unnecessary silkscreens to make the board look nicer.

To finish up, I need to improve the silkscreen and double check all the important components. 

**Time spent this session: 4 hours**
<hr>

### June 30: Final Touch Ups
Today, I finished my devboard.

<img src="https://cdn.hackclub.com/019f1bc4-65e7-7ddd-807b-8c8a0458047a/paste-1782877282813.png" alt="pcb" style="max-height:500px"> <img src="https://cdn.hackclub.com/019f1bc3-8506-71c9-912e-2b929190f20e/paste-1782877225173.png" alt="cad" style="max-height:500px">
<img src="https://cdn.hackclub.com/019f1bd8-b408-7c3a-adf7-74402bd1167b/paste-1782878612908.png" alt="cad" style="max-width:500px">

First, I assigned 3D models and LCSC part numbers to all the components using the [JLCPCB plugin](https://github.com/bouni/kicad-jlcpcb-tools) and the easyeda2kicad CLI tool. 

Next, I fixed some of the 3D models that weren't positioned properly on the devboard, such as the USB-C receptacle and header pins.

Afterwards, I worked on the silkscreen, labeling all the header pins and adding art to the back and front. I used Inkscape for the drawings.

I then exported the production files to keep in my repo, and exported the 3D model to onshape for screenshots.

**Time spent this session: 5 hours**
<hr>

### June 30 P2: Bill of Materials
I had to spend a while finding Basic components because I had earlier chosen Extended JLCPCB components.

Things I had to change were SGM --> AMS LDO.
Also the BOOT/Reset buttons had to change to a Basic version.

Creating the BOM also took a while cause I got really confused.

**Time spent this session: 4 hours**
<hr>
