# RP2040 Custom USB Interface Board (Chill Vandu)

A custom, ultra-compact RP2040-based USB interface board designed in KiCad. This board is tailored for JLCPCB SMT assembly and features USB-C, a microSD card slot (4-bit SDIO), 3 mode buttons, 3 status LEDs, and 16 MB QSPI flash.

## 📋 Project Status
- [x] Component selection & LCSC verification
- [x] Custom symbol, footprint, and 3D model generation (using `easyeda2kicad`)
- [x] Schematic capture (ERC Clean: 0 Errors)
- [ ] PCB Layout & Routing (In Progress)
- [ ] Gerber & BOM/CPL Generation
- [ ] JLCPCB Assembly & Bring-up

## 🛠️ Technical Specifications
Based on the Raspberry Pi Hardware Design guide with specific engineering modifications:
*   **MCU:** RP2040 (`C2040`) QFN-56.
*   **Power:** 500mA LDO LW5433A23E (`C20630445`) in SOT-23-5L. *Upgraded from the 200mA XC6206 to handle SD card write bursts.*
*   **USB:** USB-C 16-pin HRO TYPE-C-31-M-12 (`C165948`) with 5.1kΩ CC pulldowns, 27Ω series resistors on D+/D-, and USBLC6-2SC6 (`C7519`) ESD protection.
*   **Storage:** W25Q128JVSIQ 16MB QSPI Flash (`C97521`) and SHOU HAN TF PUSH microSD (`C393941`).
*   **User I/O:** 3 Mode buttons, 1 BOOTSEL button, 1 RESET button, and 3 Status LEDs (Red, Green, Blue).
*   **LED Circuit:** Simplified direct GPIO drive (No MOSFETs) to reduce BOM cost and board size.
*   **Expansion:** 4-pin I2C breakout (SDA, SCL, 3V3, GND) for future OLED screen/display integration. Currently unpopulated (through-holes only) to save space on the first iteration.
*   **Debugging:** 3x SWD Test Points (SWCLK, SWD, GND) for hardware recovery.

## 💻 Tools Used
*   **KiCad 10**
*   **easyeda2kicad** (for exact LCSC footprint matching)
*   **JLCPCB** (for fabrication and assembly)

## 🔗 References
*   Raspberry Pi Hardware Design with RP2040
*   JLCPCB Fabrication Toolkit
