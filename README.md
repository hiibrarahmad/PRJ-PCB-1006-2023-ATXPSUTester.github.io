<div align="center">

<img src="assets/ATXPSUTester-TOP.png" width="100%" alt="ATX PSU Tester PCB — Top View"/>

# ⚡ PRJ-PCB-1006-2023-ATXPSUTester

### ATX Power Supply Tester / Load Monitor (STM32 Nucleo-32)

**Designed by [Ibrar Ahmad](https://github.com/hiibrarahmad)**

[![PCB Version](https://img.shields.io/badge/PCB%20Version-V1.0-00c8ff?style=for-the-badge)](#)
[![Target MCU](https://img.shields.io/badge/Target-STM32L432KC%20Nucleo--32-22c55e?style=for-the-badge)](#)
[![Function](https://img.shields.io/badge/Function-ATX%20PSU%20Test%20%2F%20Load-ff6b35?style=for-the-badge)](#)

[![Last Commit](https://img.shields.io/github/last-commit/hiibrarahmad/PRJ-PCB-1006-2023-ATXPSUTester.github.io?style=for-the-badge&color=0891b2&label=Last%20Commit)](../../commits/main)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-22c55e?style=for-the-badge&logo=github)](https://hiibrarahmad.github.io/PRJ-PCB-1006-2023-ATXPSUTester.github.io/)

<br/>

[🔬 Interactive PCB View](https://hiibrarahmad.github.io/PRJ-PCB-1006-2023-ATXPSUTester.github.io/) · [📦 3D Model (STEP)](assets/ATXPSUTester.step)

</div>

---

## 📖 Project Overview

> [!NOTE]
> The designer's **first PCB, originally designed in Altium in early 2024** (internal ECO logs date to February 2024; recalled as "my first PCB from 2023"). The board's silkscreen reads "RMT project" — **RMT is a company name**, not the project's function, so it's not used as the identifier here. This overview is reconstructed from the real schematic and BOM.

An **ATX power supply tester / load monitor**, controlled by an STM32 Nucleo-32 (STM32L432KC). The schematic shows the signature ATX signals directly:

- **`PSON`** (power-supply-on), **`+12VO`**, **`+5VO`**, **`COM`** — standard ATX PSU rail/control signal names
- A **24-position, 4.2mm-pitch connector** wired to those rails — matches a standard ATX main power connector
- **Two independent MOSFET switching channels** (AUIRFZ44N, 55V TO-220 + NPN driver each) — for switching/loading rails under test
- **Two dual-op-amp (LM358P) current-sense amplifier stages** — each a shunt-resistor + gain-resistor-divider circuit, for measuring load current per channel
- **STM32 Nucleo-32** footprint (CN3/CN4, the Nucleo module's own header rows) — for control and readout

Put together: apply/switch ATX rails, load them via the two MOSFET channels, and measure the resulting current draw via the op-amp sense circuits — a classic PSU bring-up/test rig.

---

## 🖼️ PCB Preview

<table>
<tr>
<td align="center" width="50%">

**🔝 Top Side**

<img src="assets/ATXPSUTester-TOP.png" width="100%" alt="ATX PSU Tester PCB — Top View"/>

</td>
<td align="center" width="50%">

**🔻 Bottom Side**

<img src="assets/ATXPSUTester-BOT.png" width="100%" alt="ATX PSU Tester PCB — Bottom View"/>

</td>
</tr>
</table>

🔗 **[→ View Interactive PCB Online](https://hiibrarahmad.github.io/PRJ-PCB-1006-2023-ATXPSUTester.github.io/)**

---

## 📋 Key Components (from the real BOM)

| Reference | Part | Function |
|-----------|------|----------|
| Power switch ×2 | **AUIRFZ44N** (TO-220, 55V) | N-Channel Power MOSFET — rail load-switching |
| Driver ×2 | NPN Silicon Transistor (TO-92) | Gate drive for each MOSFET channel |
| Current sense ×2 | Dual Operational Amplifier, LM358P (8-pin PDIP) | Shunt current-sense amplifier |
| J10 | 24-position, 4.2mm pitch connector | ATX main power connector (PSON/+12V/+5V/COM/GND) |
| — | STM32 Nucleo-32 (STM32L432KC) | Control & readout MCU |

---

## 📁 Repository Structure

```
PRJ-PCB-1006-2023-ATXPSUTester.github.io/
│
├── assets/
│   ├── ATXPSUTester-TOP.png    ← Top view render (PNG)
│   ├── ATXPSUTester-BOT.png    ← Bottom view render (PNG)
│   └── ATXPSUTester.step        ← Real 3D model (STEP export)
│
├── index.html                    ← Interactive PCB/BOM viewer
└── README.md                     ← This file
```

---

## 🔗 Links

| Resource | URL |
|----------|-----|
| 🌐 Interactive PCB View | [hiibrarahmad.github.io/PRJ-PCB-1006-2023-ATXPSUTester.github.io](https://hiibrarahmad.github.io/PRJ-PCB-1006-2023-ATXPSUTester.github.io/) |
| 👤 Designer | [github.com/hiibrarahmad](https://github.com/hiibrarahmad) |

---

<div align="center">

**PRJ-PCB-1006-2023-ATXPSUTester**

*ATX Power Supply Tester / Load Monitor · Designed by Ibrar Ahmad*

© 2026 hiibrarahmad. All Rights Reserved.

</div>
