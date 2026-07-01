# ESP32 Breadboard Devboard

This project is an ESP32-S3-WROOM-1 devboard that can fit on a breadboard, unlike standard ESP32 DevKit V1s. I made it because my current ESP32s don't fit on a breadboard and it makes it really difficult to prototype easily, so this fixes that problem.

<img src="https://cdn.hackclub.com/019f1bc3-8506-71c9-912e-2b929190f20e/paste-1782877225173.png" alt="devboard" style="max-height:500px">

[Journal](JOURNAL.md)

## Features
- ESP32-S3-WROOM-1 Microcontroller
- 33 GPIO Pins
- 2 3.3V Pins
- 1 VCC Pin (5-12V)
- Reset + Boot Buttons
- USB-C Receptacle
- Cool Art!

## Tech Stack:
- KiCad (PCB Design)
- Onshape (CAD Renders)
- Inkscape (SVG Art Drawing)
- VS Code (Documentation)

## Images
Schematic: \
<img src="KiCad/esp32-breadboard-board/schematic.jpg" alt="schematic" style="max-width:500px"> 

PCB: \
<img src="https://cdn.hackclub.com/019f1bc4-65e7-7ddd-807b-8c8a0458047a/paste-1782877282813.png" alt="pcb" style="max-height:500px"> 

CAD (Back): \
<img src="https://cdn.hackclub.com/019f1bd8-b408-7c3a-adf7-74402bd1167b/paste-1782878612908.png" alt="cad" style="max-width:500px">

## Bill of Materials
| Manufacturer | Description | Qty | Total Price | Link |
| :--- | :--- | :---: | :--- | :--- |
| Samsung | 10uF 10V X5R 0603 Ceramic Capacitor | 6 | $0.26 | [C19702](https://jlcpcb.com/partdetail/20411-CL10A106KP8NNNC/C19702) |
| Samsung | 1uF 25V X5R 0402 Ceramic Capacitor | 2 | $0.04 | [C52923](https://jlcpcb.com/partdetail/53938-CL05A105KA5NQNC/C52923) |
| Samsung | 100nF 16V X7R 0402 Ceramic Capacitor | 6 | $0.01 | [C1525](https://jlcpcb.com/partdetail/1877-CL05B104KO5NNNC/C1525) |
| Jiangsu Changjing | B5819WSL 1A 40V SOD-123 Schottky Diode | 2 | $0.06 | [C8598](https://jlcpcb.com/partdetail/9093-B5819WSL/C8598) |
| Hubei KENTO | Red LED Water Clear 0603 | 2 | $0.01 | [C2286](https://jlcpcb.com/partdetail/Hubei_KENTOElec-KT0603R/C2286) |
| UNI-ROYAL | 0Ω 0402 Thick Film Resistor | 2 | $0.01 | [C17168](https://jlcpcb.com/partdetail/17853-0402WGF0000TCE/C17168) |
| UNI-ROYAL | 5.1kΩ 0402 1% Resistor | 4 | $0.01 | [C25905](https://jlcpcb.com/partdetail/26648-0402WGF5101TCE/C25905) |
| UNI-ROYAL | 2.2kΩ 0402 1% Resistor | 2 | $0.01 | [C25879](https://jlcpcb.com/partdetail/26622-0402WGF2201TCE/C25879) |
| UNI-ROYAL | 10kΩ 0402 1% Resistor | 4 | $0.01 | [C25744](https://jlcpcb.com/partdetail/26487-0402WGF1002TCE/C25744) |
| XUNPU | 4x3mm SMD Tactile Switch (Button) | 4 | $0.22 | [C720477](https://jlcpcb.com/partdetail/XUNPU-TS_1088AR02016/C720477) |
| STMicroelectronics| USBLC6-2SC6 SOT-23-6 ESD Protection | 5 | $0.83 | [C7519](https://jlcpcb.com/partdetail/STMicroelectronics-USBLC62SC6/C7519) |
| Advanced Monolithic | AMS1117-3.3V 1A LDO SOT-223 | 2 | $0.40 | [C6186](https://jlcpcb.com/partdetail/Advanced_MonolithicSystems-AMS1117_33/C6186) |
| Korean Hroparts | Type-C 16-Pin Female SMD USB Connector | 2 | $0.37 | [C165948](https://jlcpcb.com/partdetail/Korean_HropartsElec-TYPE_C_31_M12/C165948) |
| Espressif Systems | ESP32 Wi-Fi & Bluetooth Module | 1 | $4.77 | [C2913198](https://www.lcsc.com/product-detail/C2913198.html) |
| BOOMELE | 1x20P 2.54mm Pin Header | 5 | $0.78 | [C50981](https://www.lcsc.com/product-detail/C50981.html) |

<br>

### Manufacturing & Cost Summary

| Item / Service | Qty | Price |
| :--- | :---: | :--- |
| **PCB Manufacturing** (JLCPCB) | 5 | $2.00 |
| **PCB Assembly / PCBA** (JLCPCBA) | 2 | $19.15 |
| **Components Subtotal** | - | $7.79 |=
| JLCPCB Shipping (GSDL) | - | $3.12 |
| LCSC Shipping (GSDL) | - | $8.00 |
| LCSC Handling Fee | - | $5.00 |
| **Total Project Cost** | | **$42.82** |

---

## Motivation
I made this project to make ESP32 modules usable on a devboard. It also helped me develop my PCB skills. I also want to present my design at Open Sauce 2026. 