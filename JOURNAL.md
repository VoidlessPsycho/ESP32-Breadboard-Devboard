# ESP32 Breadboard Devboard Journal

### June 28, 2026: Created Schematic
Today, I wanted to make an ESP32 Devboard. I had previously had problems with ESP32 because all the modules I found were too wide to fit on a breadboard. This is why I decided to embark on creating my own ESP32 devboard that would fit on a breadboard.

First, I selected which ESP32 microcontroller I wanted to use as the core of my project. There were many different types, such as the ESP32-S3 and -C3. I decided on using the ESP32-S3-WROOM-1 Module because it had a good balance of most features and less complexity. I used Gemini/ChatGPT for advice and also looked through an Instructables guide and the EspressIF documentation and hardware references.

I started with the WROOM module in the center. Then, I added the USB-C receptacle, the 14-pin one as it worked for USB 2.0 and had a simplified schematic to make it easier to route everything. I first used the AP2112K-3.3TRG1 low-dropout regulator to convert the 5v from the USB to the 