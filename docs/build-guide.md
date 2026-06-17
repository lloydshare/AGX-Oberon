# AGX Oberon - Build Guide

**Project**: AGX Oberon  
**Version**: Early Test Build (June 2026)  
**Builder**: Lloyd Share

Note: this is not complete yet

This guide documents how the current AGX Oberon system was built.

---

## Warning

- This is an advanced / experimental build using salvaged enterprise and console-derived hardware.
- High power consumption and custom power delivery involved — work safely.
- Water cooling and server PSUs carry risk of shorts or damage if not done correctly.
- Proceed at your own risk.

---

## Parts List (Current Build)

See [`hardware-specs.md`](../hardware-specs.md) for full detailed specifications.

### Core Components
- AMD BC-250 mainboard (Oberon-derived APU)
- 2× NVIDIA Tesla V100 SXM2 (water cooled)
- Samsung PM991 256GB NVMe SSD
- Samsung 850 EVO 250GB SATA SSD
- HP ProLiant DL380 1600W server PSU
- Corsair CX650F 650W modular PSU

### Expansion & Peripherals
- M.2 NVMe to 9-Port SATA III Adapter
- Creative Sound BlasterX AE-5 Plus
- Intel Wi-Fi 6 AX200 PCIe card
- Elektron Overhub 7-Port USB 3.0 Hub
- OneRNG v3.0
- 8Bitdo Wireless USB Adapter 2

---

## Build Steps

### 1. Base Board Preparation
1. Inspect the BC-250 board for damage.
2. Clean all contacts and PCIe slots.
3. Install the M.2 NVMe to 9-Port SATA adapter in the appropriate PCIe slot.
4. Install the Intel Wi-Fi 6 AX200 card.
5. Install the Creative Sound BlasterX AE-5 Plus.
6. Connect onboard USB headers if needed (2× USB 2.0 + 2× USB 3.0 available).

### 2. Memory & Storage
- The BC-250 uses 16GB GDDR6 soldered unified memory (no DIMM slots).
- Install NVMe SSD as primary boot drive.
- Connect SATA SSD and any additional drives to the 9-port adapter.

### 3. GPU Installation
1. Mount the 2× Tesla V100 SXM2 modules (ensure proper SXM2 connectors / power delivery).
2. Connect water cooling blocks to both V100s and the APU if supported.
3. Route cooling tubes to the 1 radiator + fans.

### 4. Power Delivery (Critical)
- Use the **HP 1600W** server PSU for the main 12V rail (powers the BC-250 and GPUs).
- Use the **Corsair CX650F** for 5V / 3.3V rails and peripherals (server PSU lacks these).
- Carefully wire the power connections — polarity and pinouts must be verified.
- **Future goal**: Single high-wattage PSU solution.

### 5. Cooling Setup
- Install water block(s) on APU and V100s.
- Mount 1 radiator + fans in the case.
- Ensure good airflow around the board.

### 6. Peripherals & Final Assembly
- Connect USB hub, wireless adapter, OneRNG, etc.
- Attach DisplayPort cable from onboard iGPU output.
- Connect Ethernet, audio, etc.

### 7. Initial Boot
1. Power on and enter BIOS.
2. Set boot order to NVMe SSD.
3. Configure any available performance / power settings.
4. Install OS (Windows 11 or custom Linux).

---

## Current Case Situation

- Temporary open-air / test bench setup
- Planning a fully custom compact case in the future

---

## Known Challenges & Workarounds

- No DDRx RAM support → Relying entirely on unified GDDR6 + HBM2e
- ROCm not supported on BC-250 → Using CUDA via V100s
- Power delivery is split between two PSUs
- Limited native USB ports (mitigated with hub)

---

## Next Phases

- Add 2 more V100 SXM2 GPUs
- Build custom compact case
- Advanced power management / PDU
- Full water cooling optimization
- Benchmarking and tuning

---

## Tips from the Builder

- Double-check all power connections multiple times.
- Monitor temperatures closely during first stress tests.
- Document every change you make.

Contributions and improvements welcome!

---

**AGX Oberon**

*Last updated: June 17, 2026*
