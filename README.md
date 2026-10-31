# RP2040 Custom USB Interface Board (Chill Vandu)

A custom RP2040-based USB interface board designed in KiCad. This board is tailored for JLCPCB SMT assembly and features USB-C, a microSD card slot (4-bit SDIO), 3 mode buttons, 3 status LEDs, and 16 MB QSPI flash.

## 📋 Project Status
- [x] Component selection & LCSC verification
- [x] Custom symbol, footprint, and 3D model generation (using `easyeda2kicad`)
- [x] Schematic floorplanning (all components placed on canvas)
- [ ] Schematic wiring (In Progress)
- [ ] PCB Layout & Routing
- [ ] Gerber & BOM/CPL Generation

## 🛠️ Technical Specifications & Corrections
Based on the Raspberry Pi Hardware Design guide and custom engineering checks:
*   **MCU:** RP2040 (`C2040`) QFN-56.
*   **Power:** 500mA LDO LW5433A23E (`C20630445`) in SOT-23-5L. *Upgraded from the 200mA XC6206 to handle SD card write bursts.*
*   **USB:** USB-C 16-pin HRO TYPE-C-31-M-12 (`C165948`) with 5.1kΩ CC pulldowns and 27Ω series resistors on D+/D-.
*   **Storage:** W25Q128JVSIQ 16MB QSPI Flash (`C97521`) and SHOU HAN TF PUSH microSD (`C393941`).
*   **LEDs:** Direct GPIO drive (No MOSFETs) to simplify BOM. 
*   **ESD Protection:** USBLC6-2SC6 (`C7519`) on USB data lines.

## 💻 Tools Used
*   **KiCad 10**
*   **easyeda2kicad** (for exact LCSC footprint matching)
*   **JLCPCB** (for fabrication and assembly)

## 🔗 References
*   Raspberry Pi Hardware Design with RP2040
*   JLCPCB Fabrication Toolkit
