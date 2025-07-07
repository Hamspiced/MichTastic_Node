## Michigan’s Own Low-Power, Low-Form-Factor LoRa Node for Meshtastic

Simple NRF52840 / E22 Meshtastic node in an ultra-small form factor.

---

### 🛠️ Installation Method

1. **Solder the E22 Module**  
   Use hot air or a hotplate to solder the E22 to the backside of the board.

2. **Install Pin Headers**  
   Solder pin headers on the front side of the board, bottoming them out on the E22.

3. **Battery Connection (Optional)**  
   If you want a directly connected battery, solder the two jumpers on the bottom of the MCU.

4. **Battery Voltage Reporting (Optional)**  
   - `R1` and `R2` can remain unpopulated if you don’t need battery voltage monitoring.

5. **Fuse Configuration (Optional)**  
   - `F1` and `F2` can be jumpered.  
   - These are resettable fuses for those of us who can’t always follow `P+` and `P-` directions (like me).

---

### 💾 Flashing Meshtastic Firmware

1. **Put the Board in Bootloader Mode**  
   - Connect the USB cable to your computer and Pro-micro
   - With a small metal object, short the **GND** and **RST** pin on the Pro-micro quickly **twice**
   - The board should appear as a USB drive

2. **NEW BOARDS ONLY: Update the NICE_NANO Pro-micro Bootloader**
   - If this is your first use of a new Pro-Micro, a bootloader upgrade is required
   - Download and unzip the Pro-micro_bootloader_update.zip file.
   - **DO NOT COPY BOTH FILES AT THE SAME TIME**
   - Copy the Hex file **FIRST** and drop it onto the USB drive
   - Then copy the UF2 file **NEXT** and drop it onto the USB drive
   - The drive will disconnect
   - Unplug the device and keep it powered off for 10 seconds.
   - Plug it back in and start over with #3
   - YOU WILL NOT BE DOING THIS AGAIN.

3. **Flash via Meshtastic Flasher (Recommended)**  
   - Download firmware from [Meshtastic Flasher](https://flasher.meshtastic.org).
   - Select "NRF52 Pro-micro DIY" 
   - Select your firmware version.
   - Click **Download** and wait for completion.
   - Drag the downloaded firmware file to the Pro-micro USB drive.
   - The drive will disconnect
   - Unplug the device and keep it powered off for 10 seconds.

   **OR**

**Flash via Command Line**

4. **Install Dependencies**  
   Make sure you have Python and the `esptool` or `nrfutil` utilities installed.  
   > For NRF52840 boards, you can also use the Meshtastic Flasher GUI or `dfu-util`.

5. **Download Firmware**  
   - Get the latest NRF52 firmware release `.zip` or `.hex` file from the [Meshtastic releases page](https://github.com/meshtastic/firmware/releases).
  

   - Example using `nrfutil`:
     ```bash
     nrfutil dfu usb-serial -pkg firmware.zip -p /dev/ttyACM0
     ```
   - Replace `/dev/ttyACM0` with the correct serial port.

6. **Verify Flashing**  
   - After flashing, the device should reboot.
   - Use the Meshtastic app or CLI to connect and configure.

---

### 💬 Community

Join the Michigan Meshtastic community on Discord:  
[https://discord.gg/jXtpzh4B](https://discord.gg/jXtpzh4B)

---

### 📝 License

This project is released under a **Non-Commercial Open Source License**.  
You are free to use, modify, and share this design for **non-commercial purposes only**.  
Commercial use requires explicit permission from the author.

---

✅ **Tip:** For more detailed instructions, see [meshtastic.org/docs](https://meshtastic.org/docs).

---
