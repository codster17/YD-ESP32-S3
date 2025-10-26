# YD-ESP32-S3 Core Board  

### Introduction  

The **YD-ESP32-S3 Core Board** was designed by **VCC-GND Studio**.  
For details or to purchase, visit [www.vcc-gnd.com](https://www.vcc-gnd.com).  

This device uses the **ESP32-S3** chip — perfect for IoT prototyping *and* real-world applications.  
It includes **two USB ports**:  
- One is a hardware **USB-to-UART converter (CH343P, by WCH)**  
- The other is the **native ESP32-S3 USB interface**

![](/IMG/img1.PNG)

This guide helps you get started quickly with the YD-ESP32-S3 and provides detailed info about the board.

YD-ESP32-S3 is an entry-level development board featuring the **ESP32-S3-WROOM-1 Wi-Fi + Bluetooth® LE module**.  
Most pins from the onboard module are broken out on both sides of the board for easy prototyping.  
You can use jumper wires, plug it into a breadboard, or integrate it into your own circuits.

![](/IMG/YD-ESP32-S3.PNG)

Key points:
1. It’s a minimal core board built around Espressif’s **ESP32-S3 module**.  
2. Dedicated **LDO circuit** ensures stable power for wireless features.  
3. Includes a **WS2812 RGB LED** (note: not driven directly by GPIO).  
4. **RST button** for external reset, **BOOT button** (with RST) enters bootloader mode — after boot, it functions as a user button on **GPIO0**.  
5. Two **USB Type-C** ports:  
   - One is **native USB (GPIO19/GPIO20)**  
   - One is **USB-to-UART (CH343)**

---

### Hardware Overview  

![](/IMG/img2.png)

| Component | Description |
| :-- | :-- |
| **ESP32-S3-WROOM-1** | General-purpose Wi-Fi + Bluetooth MCU module with rich interfaces and strong AI processing capability. Designed for AIoT applications. Uses onboard PCB antenna. |
| **5V → 3.3V LDO** | Power converter (input 5V, output 3.3V @ 1A). |
| **Pin Headers** | All usable GPIOs (except flash SPI bus) are broken out to headers. |
| **USB-to-UART Port** | Type-C USB port for power, flashing firmware, and serial communication via CH343P bridge. |
| **Boot Button** | Press **BOOT** and then **RESET** to enter firmware download mode. After boot, it can be used as a regular input (GPIO0). |
| **Reset Button** | Hardware reset. |
| **USB Port** | Native ESP32-S3 USB OTG port (Full-Speed USB 1.1). Can power the board, flash firmware, communicate via USB, or be used for JTAG debugging. |
| **USB-to-UART Bridge** | **CH343P** by **WCH** ([link](http://www.wch-ic.com/products/CH343.html)). |
| **RGB LED** | Addressable **WS2812 RGB LED**, driven by **GPIO48**. |
| **PWR LED** | Power indicator (always on when powered, not software-controlled). |
| **TX LED** | Connected to ESP32-S3 UART TX line (GPIO43), blinks when sending serial data. |
| **RX LED** | Connected to UART RX line (GPIO44), blinks when receiving data. |

---

### Notes  
Pins **GPIO35**, **GPIO36**, and **GPIO37** are internally connected to SPI flash/PSRAM (8-line mode) and are **not available for external use**.

---

### Getting Started  
Before powering up, ensure the board is undamaged.

---

### Block Diagram  
![](/IMG/img4.png)

---

### Power Options  
You can power the board via:  
1. **USB-to-UART port** or **ESP32-S3 USB port** (recommended, either or both)  
2. **5V + GND pins**  
3. **3.3V + GND pins**

---

### Pin Headers  
Pin names correspond to the schematic numbering.

#### P1 Header  

| No | Name | Type | Function |
| :- | :- | :- | :- |
| 1 | 3V3 | P | 3.3V Power |
| 2 | 3V3 | P | 3.3V Power |
| 3 | RST | I | EN |
| 4 | 4 | I/O/T | RTC_GPIO4, GPIO4, TOUCH4, ADC1_CH3 |
| 5 | 5 | I/O/T | RTC_GPIO5, GPIO5, TOUCH5, ADC1_CH4 |
| 6 | 6 | I/O/T | RTC_GPIO6, GPIO6, TOUCH6, ADC1_CH5 |
| 7 | 7 | I/O/T | RTC_GPIO7, GPIO7, TOUCH7, ADC1_CH6 |
| 8 | 15 | I/O/T | RTC_GPIO15, GPIO15, U0RTS, ADC2_CH4, XTAL_32K_P |
| 9 | 16 | I/O/T | RTC_GPIO16, GPIO16, U0CTS, ADC2_CH5, XTAL_32K_N |
| 10 | 17 | I/O/T | RTC_GPIO17, GPIO17, U1TXD, ADC2_CH6 |
| 11 | 18 | I/O/T | RTC_GPIO18, GPIO18, U1RXD, ADC2_CH7, CLK_OUT3 |
| 12 | 8 | I/O/T | RTC_GPIO8, GPIO8, TOUCH8, ADC1_CH7, SUBSPICS1 |
| 13 | 3 | I/O/T | RTC_GPIO3, GPIO3, TOUCH3, ADC1_CH2 |
| 14 | 46 | I/O/T | GPIO46 |
| 15 | 9 | I/O/T | RTC_GPIO9, GPIO9, TOUCH9, ADC1_CH8, FSPIHD |
| 16 | 10 | I/O/T | RTC_GPIO10, GPIO10, TOUCH10, ADC1_CH9, FSPICS0 |
| 17 | 11 | I/O/T | RTC_GPIO11, GPIO11, TOUCH11, ADC2_CH0, FSPID |
| 18 | 12 | I/O/T | RTC_GPIO12, GPIO12, TOUCH12, ADC2_CH1, FSPICLK |
| 19 | 13 | I/O/T | RTC_GPIO13, GPIO13, TOUCH13, ADC2_CH2, FSPIQ |
| 20 | 14 | I/O/T | RTC_GPIO14, GPIO14, TOUCH14, ADC2_CH3, FSPIWP |
| 21 | 5V | P | 5V Power |
| 22 | G | G | Ground |

#### P2 Header  

| No | Name | Type | Function |
| :- | :- | :- | :- |
| 1 | G | G | Ground |
| 2 | TX | I/O/T | U0TXD, GPIO43 |
| 3 | RX | I/O/T | U0RXD, GPIO44 |
| 4 | 1 | I/O/T | RTC_GPIO1, GPIO1, TOUCH1, ADC1_CH0 |
| 5 | 2 | I/O/T | RTC_GPIO2, GPIO2, TOUCH2, ADC1_CH1 |
| 6 | 42 | I/O/T | MTMS, GPIO42 |
| 7 | 41 | I/O/T | MTDI, GPIO41 |
| 8 | 40 | I/O/T | MTDO, GPIO40 |
| 9 | 39 | I/O/T | MTCK, GPIO39 |
| 10 | 38 | I/O/T | GPIO38 |
| 11 | 37 | I/O/T | GPIO37 |
| 12 | 36 | I/O/T | GPIO36 |
| 13 | 35 | I/O/T | GPIO35 |
| 14 | 0 | I/O/T | GPIO0 |
| 15 | 45 | I/O/T | GPIO45 |
| 16 | 48 | I/O/T | GPIO48, RGB LED |
| 17 | 47 | I/O/T | GPIO47 |
| 18 | 21 | I/O/T | GPIO21 |
| 19 | 20 | I/O/T | GPIO20, USB_D+ |
| 20 | 19 | I/O/T | GPIO19, USB_D- |
| 21 | G | G | Ground |
| 22 | G | G | Ground |

**Legend:**  
P = Power, I = Input, O = Output, T = Tri-state (high impedance)

---

### Pinout Diagram  
![](/IMG/img11.jpg)

---

### CH340 Driver  
Official download:  
- [English](http://www.wch-ic.com/products/CH340.html)  
- [Chinese](https://www.wch.cn/products/CH340.html?from=list)

---

### Micropython Firmware  
Use **flash_download_tool_3.9.2_0** for Windows to flash firmware.  
No installation needed — unzip and run.  
Select **ESP32-S3 → Develop → USART**, start address `0x00`.  
If flashing fails, reinstall the USB-to-UART driver (CH343).

![](/IMG/img3.png)

⚠️ **Important:**  
- Do **not** use Thonny’s built-in ESP32 flasher (it’s for the older ESP32, not S3).  
- Do **not** use the official Micropython firmware with PSRAM — it won’t run correctly.  
- Use **Espressif’s Flash Tool**, select ESP32-S3, port = COM (USB), and use VCC-GND’s custom firmware (start address `0x00`).  
- Erase flash before downloading.  
- Update CH343 drivers and confirm the COM port shows up in Device Manager.

Tasmota firmware: [https://tasmota.github.io/docs/](https://tasmota.github.io/docs/)

Official Espressif tools: [https://www.espressif.com.cn/en/home](https://www.espressif.com.cn/en/home)

All related resources (drivers, firmware, schematics, etc.):  
[http://124.222.62.86/yd-data/YD-ESP32-S3/](http://124.222.62.86/yd-data/YD-ESP32-S3/)

Programming references:  
- **ESP-IDF (C):** [ESP-IDF Getting Started (ESP32-S3)](https://docs.espressif.com/projects/esp-idf/en/latest/esp32s3/get-started/index.html)  
- **Arduino:** [Arduino-ESP32 Docs](https://docs.espressif.com/projects/arduino-esp32/en/latest/getting_started.html)  
- **Micropython:** [ESP32 Quick Reference](https://docs.micropython.org/en/latest/esp32/quickref.html)

---

### Counterfeit & Clone Boards  

There are many fake or low-quality copies of YD boards, especially in Shenzhen Huaqiangbei.  
Here’s why you should avoid them:

1. Fake units often use **refurbished or unofficial components**.  
2. WS2812 LEDs not connected or missing.  
3. No factory QC — shipped right off production line.  
4. Incorrect silkscreens copied blindly.  
5. Clones use **outdated v1.2 PCB**, official version is **v1.4**.  
6. Poor RF design → high power use, weak Wi-Fi/Bluetooth, frequent crashes.  
7. Wrong LDOs (like 1117), high dropout → instability.  
8. Cheap diodes cause voltage loss → unstable system.  
9. No technical support; docs are copied from old versions.  
10. Boot issues — stuck in bootloader.  
11. No schematics → users can’t troubleshoot.

Some clones even print the **“YD-ESP32”** name or the **VCC-GND.COM** website — these are counterfeit and illegal.  
Please support genuine VCC-GND products ❤️

---

### GPIO Matrix Flexibility  

ESP32 series chips feature a **flexible internal IO matrix**, meaning interfaces like **I²C, I²S, UART, SPI**, etc., can be mapped to *any* GPIO.  
That’s why function diagrams don’t show fixed pins — you can assign these peripheral functions dynamically in software.
