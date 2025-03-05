# ESP8266 WLED LED Control

This project uses an **ESP8266 D1 Mini** with **WLED** firmware to control a **WS2812B LED strip** and allows preset selection using two **push buttons**.

## Hardware Components
- **ESP8266 D1 Mini**
- **WS2812B LED strip** (20 LEDs)
- **2 x Push buttons**
- **2 x 100kΩ pull-up resistors**
- **Power supply (5V, at least 2A)**

## Wiring Diagram
- **LED Strip**: Data pin connected to **GPIO2 (D4)**
- **Button 0**: Connected to **GPIO1 (TX)** with a **100kΩ pull-up resistor**
- **Button 1**: Connected to **GPIO3 (RX)** with a **100kΩ pull-up resistor**

## WLED Configuration
1. Flash **WLED** onto the ESP8266.
2. Configure LED settings:
   - LED GPIO: **D4 (GPIO2)**
   - LED count: **20**
3. Set up **Button Actions** under **Time & Macros**:
   - **Button 0 (GPIO1 - TX)**
     - Short press → Assigns a preset (solid color)
     - Long press → Turns LEDs off
     - Double press → Assigns another preset
   - **Button 1 (GPIO3 - RX)**
     - Short press → Assigns a preset (solid color)
     - Long press → Turns LEDs off
     - Double press → Assigns another preset
4. Save the configuration and reboot.


## Setup Instructions 
## Connecting the ESP8266 D1 Mini to a PC & Checking the Serial Port
1. **Connect the ESP8266 D1 Mini to your PC** using a **Micro-USB cable**.
2. **Ensure you have the correct USB drivers** installed:
   - For CH340G-based boards, install the [CH340 driver](https://www.wch.cn/download/CH341SER_EXE.html).
   - For CP2102-based boards, install the [CP210x driver](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers).
3. **Open Device Manager** (Press `Win + X`, then select **Device Manager**).
4. Expand the **Ports (COM & LPT)** section.
5. Look for a device named **USB-SERIAL CH340** or **CP210x USB to UART Bridge**.
6. Note the **COM port number** (e.g., `COM3`, `COM5`, etc.).
7. Use this COM port in your preferred serial monitor (e.g., Arduino IDE, PuTTY, or a Python script) to communicate with the ESP8266.

## Flashing WLED onto ESP8266 D1 Mini
1. Go to [WLED Web Installer](https://install.wled.me/) and follow the instructions to install WLED on the ESP8266 D1 Mini device.

## Connecting to the ESP8266 D1 Mini Wi-Fi
1. **Power on the ESP8266 D1 Mini.**
2. **Look for a Wi-Fi network** named `WLED-AP` in your device's Wi-Fi settings.
3. **Connect to `WLED-AP`** (default password: `wled1234`).
4. **Open a web browser** and navigate to `http://4.3.2.1/` to access the WLED web interface.
5. **Go to the Wi-Fi settings in WLED** and enter your home Wi-Fi credentials.
6. **Reboot the ESP8266**; it will now connect to your home network.
7. **Find the ESP8266's new IP address** by checking your router's DHCP list or using an IP scanner.
8. **Access WLED from your network** by entering the new IP address in a web browser.

### Configuring the LED Strip
1. Go to **Settings** > **LED Preferences** in the WLED web interface.
2. Set **LED Output GPIO** to **D4 (GPIO2)**.
3. Set **LED count** to **20**.
4. Save settings and reboot.

### Configuring Button Actions
1. Go to **Settings** > **Time & Macros** > **Button Actions**.
2. Assign **Button 0 (GPIO1 - TX)**:
   - Short press → Preset for solid color
   - Long press → Turns LEDs off
   - Double press → Another preset
3. Assign **Button 1 (GPIO3 - RX)**:
   - Short press → Preset for solid color
   - Long press → Turns LEDs off
   - Double press → Another preset
4. Save settings and restart WLED.

## Button Actions Documentation 
### Button 0 (GPIO1 - TX)
- **Short press:** Assigns a solid color preset (e.g., blue or red).
- **Long press:** Turns off the LED strip.
- **Double press:** Assigns another preset (e.g., rainbow effect).

### Button 1 (GPIO3 - RX)
- **Short press:** Assigns a solid color preset.
- **Long press:** Turns off the LED strip.
- **Double press:** Assigns another preset.


### Wiring Diagram
<img width="647" alt="WLED Wiring Diagram" src="https://github.com/user-attachments/assets/2baa67e3-dd93-4337-8142-be4f797d691a" />




## License
This project is open-source under the **MIT License**.

