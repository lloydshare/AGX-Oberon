# AGX Oberon - Hardware Specifications

**Project**: AGX Oberon  
**Version**: Early Test Build (June 2026)  
**Builder**: Lloyd Share

---

## Core System

| Component                    | Specification                                      | Details |
|------------------------------|----------------------------------------------------|---------|
| **Mainboard**                | AMD BC-250 (Cyan Skillfish / Ariel)               | PS5-derived mining/server board |
| **APU**                      | 6-core / 12-thread Zen 2 CPU + 24 CU RDNA2 iGPU   | Oberon-derived |
| **CPU Clock**                | 3.5 GHz (stock / fixed)                           | Up to ~3.85 GHz possible with mods |
| **iGPU Architecture**        | RDNA2 (gfx1013)                                    | 24 Compute Units (1536 Shaders) |
| **iGPU Clock**               | 1500–2000 MHz (stock)                             | Up to 2230 MHz with kernel patches |
| **Unified Memory**           | 16GB GDDR6                                        | Shared between CPU & iGPU |
| **HBM2e Memory**             | 32GB (from 2× V100)                               | - |
| **Total System Memory**      | 48GB                                              | 16GB GDDR6 + 32GB HBM2e |
| **System RAM Type**          | None                                              | No DDRx DIMMs |

---

## Onboard I/O & Video

| Feature                      | Specification                                      |
|------------------------------|----------------------------------------------------|
| **Video Output**             | 1× DisplayPort (from iGPU)                        |
| **Onboard Audio**            | Realtek ALC audio codec (standard onboard audio)  |
| **Onboard Wired Network**    | Gigabit Ethernet (Realtek or equivalent)          |
| **Onboard USB**              | 2× USB 2.0 + 2× USB 3.0 ports                     |

---

## Compute Performance (Theoretical Peaks)

| Component                  | Quantity | FP32 TFLOPs | FP16 / Tensor TFLOPs | Notes |
|----------------------------|----------|-------------|----------------------|-------|
| **APU iGPU**               | 1        | ~7.7–9.2    | ~15–18               | At 2000–2230 MHz |
| **NVIDIA Tesla V100 SXM2** | 2×       | 31.4        | 250                  | 15.7 FP32 + 125 Tensor each |
| **Total Compute**          | -        | **~39+**    | **~265+**            | Current build |
| **Planned (4× V100)**      | 4×       | **~62+**    | **~500+**            | Target goal |

---

## Discrete Accelerators

| Component                  | Quantity | Specs |
|----------------------------|----------|-------|
| **NVIDIA Tesla V100 SXM2** | 2×       | Volta architecture, 5120 CUDA cores each, 640 Tensor cores each, 16GB HBM2 per card, water cooled |
| **GPU Clock (V100)**       | -        | Boost up to 1530 MHz |
| **Totals**            | 32GB total | HBM2 @ 900 GB/s per card, 10240 CUDA cores, 1280 Tensor cores |

*(Planned: +2× V100 SXM2 for 4× total)*

---

## Storage

| Device                          | Capacity     | Interface          | Notes |
|---------------------------------|--------------|--------------------|-------|
| Samsung PM991 NVMe SSD          | 256GB        | PCIe NVMe          | Boot drive |
| Samsung 850 EVO SATA SSD        | 250GB        | SATA III           | Secondary |
| **SATA Expansion**              | 9 ports      | M.2 PCIe Adapter   | SATA III 6Gbps |

---

## Networking & Connectivity

- **Wired**: Onboard Gigabit Ethernet
- **Wi-Fi / Bluetooth**: Intel Wi-Fi 6 AX200 (up to 2400 Mbps) + BT 5.0
- **USB Expansion**: Elektron Overhub 7-Port USB 3.0 Hub
- **Wireless Gaming**: 8Bitdo Wireless USB Adapter 2

---

## Audio

- **Onboard**: Realtek ALC codec
- **Dedicated**: Creative Labs Sound BlasterX AE-5 Plus (PCIe)

---

## Power Supply

| PSU Model                          | Wattage   | Notes |
|------------------------------------|-----------|-------|
| HP ProLiant DL380 Enterprise       | 1600W     | 12V only (server-grade) |
| Corsair CX650F RGB                 | 650W      | Full modular (5V/3.3V rails) |

**Goal**: Transition to single high-wattage PSU.

---

## Cooling

- **Type**: Hybrid water cooling (1 radiator + multiple fans)
- **Cooled Components**: APU + 2× V100 SXM2

---

## Additional Components

- **Hardware RNG**: OneRNG v3.0 USB Open Hardware Random Number Generator

---

## Current Status & Notes

- **Compute Focus**: Strong unified memory + HBM2e setup, ideal for large language models
- **Software Support**: CUDA + Vulkan (ROCm currently not supported on BC-250)
- **Status**: Early testing phase
- **Power Consumption**: Expected 400–800W under full load

---

**AGX Oberon**

*Last updated: June 17, 2026*
