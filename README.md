# AGX Oberon

**A budget personal AI/Gaming workstation built on PS5 (Oberon) silicon.**

Turning salvaged enterprise server hardware and PS5-derived AMD BC-250 boards (Cyan Skillfish / Ariel — the PS5 APU) into a compact, high-performance machine for local LLMs, inference, training, AI development, and AAA 1080p/1440p gaming.

---

## Project Goals

- Build a high-performance AI/Gaming workstation at a fraction of DGX Spark / Ryzen AI Halo cost
- Leverage the excellent unified GDDR6 memory of the Oberon APU + discrete GPUs
- Push beyond 500 TFLOPs of compute
- Fully document the build so others can replicate or improve it
- Work around hardware limitations of the BC-250 (console-derived silicon)
- Excellent Windows and Linux support (including custom high-performance kernel)
- Advanced power management and thermal tuning
- Discover the real resource limits of the BC-250 platform
- Optional hybrid AMD + NVIDIA GPU support

## Current Hardware (Working)

- **Mainboard**: AMD BC-250
- **APU**: 6-core Zen 2 + 24 CU RDNA2 (Oberon-derived)
- **Discrete GPUs**: 2× NVIDIA Tesla V100 SXM2
- **Memory**: 16GB GDDR6 (unified) + 32GB HBM2e (No DDRx RAM)
- **Storage**:
  - Samsung PM991 256GB NVMe SSD
  - Samsung 850 EVO 250GB SATA SSD
- **Expansion**:
  - M.2 NVMe PCIe M-Key to 9-Port SATA III Adapter
  - Creative Sound BlasterX AE-5 Plus
  - Intel Wi-Fi 6 AX200 + Bluetooth 5.0
  - Elektron Overhub 7-Port USB 3.0 Hub
- **Peripherals**:
  - 8Bitdo Wireless USB Adapter 2
  - OneRNG v3.0 Hardware Random Number Generator
- **Power**:
  - HP ProLiant DL380 1600W Enterprise PSU (12V only)
  - Corsair CX650F RGB 650W Modular PSU
- **Cooling**: Water cooling (1 radiator + multiple fans)

**Status**: Early test phase — Planning to add 2 more V100s + SATA Blu-ray drive.

---

## Current Features

- Strong unified + HBM memory for large local models
- CUDA + Vulkan support (ROCm not supported on this platform)
- 9× SATA ports
- Water-cooled setup
- Currently over 250 TFLOPs compute
- Steam machine
- Custom Bios

## Desired / Planned Features

- Custom compact PC case
- Analogue A/V signal processing (for game emulation)
- RF laboratory / wireless signal analysis capabilities
- Advanced PDU, thermal, and power management
- Two additional NVIDIA V100 GPUs + enhanced cooling
- Single PSU operation
- Expanded storage

---

## Getting Started

### Hardware Build, Configurations & Costs
See [`docs/build-guide.md`](docs/build-guide.md)

### BIOS Setup
See [`docs/bios-setup.md`](docs/bios-setup.md)

### Software & LLM Setup
See [`docs/llm-setup.md`](docs/llm-setup.md)

## Benchmarks

*(Coming soon — tokens/s on 7B, 13B, 34B, 70B+ models with Ollama, llama.cpp, etc.)*

## Gallery

*(Photos and build log coming soon)*

## Community & Contributions

Feel free to open issues, submit PRs, or share your own BC-250 / Oberon builds!

## License

MIT License

---

**Made by Lloyd Share • 2026**  
**AGX Oberon**
