# 🔌 Snippet — PCB Development

Welcome to the hardware side of **Snippet**! 🖥️✨ Snippet is a small display that plugs into your PC to show bite-sized info: the media that's playing 🎵, system diagnostics 📊, the time and date 🕒, and more.

This repo holds the **Altium Designer** project for the Snippet board. The display software lives in [Project-Snippet/Snippet](https://github.com/Project-Snippet/Snippet) 🦀.

---

## 👥 Contributors
☎️ Ollie Livingston ([@OllieL1](https://github.com/OllieL1)) \
⚙️ Adam Tong ([@AdamTong04](https://github.com/AdamTong04))

---

## 🧠 The Brains: STM32F303RET6

| Spec | Value |
| --- | --- |
| 🏷️ Part | STMicroelectronics **STM32F303RET6** (U1) |
| ⚡ Core | ARM Cortex-M4F, 32-bit, up to 72 MHz |
| 💾 Memory | 512 KB Flash, 80 KB SRAM |
| 📦 Package | LQFP-64 (10 × 10 mm) |
| 🔋 Supply | 2.0 – 3.6 V (VDD / VDDA) |
| 🔗 Has | USB FS, SPI, I²C, UART, ADCs, timers, SWD debug |

---

## 🛠️ Getting Started
1. 💻 Install **Altium Designer** (the project was made in a recent version with Altium 365 content).
2. 📥 Clone this repo.
3. 📂 Open `Snippet_PCB_v1/Snippet_PCB_v1.PrjPcb`.
4. ✅ Run **Project → Validate PCB Project** before you make changes.

---

## 🎯 Goals & Progress

### 📝 Schematic
- [x] 🏗️ Set up the Altium project
- [x] 🧠 Place and annotate the STM32F303RET6 MCU (U1)
- [x] 🔋 Power input: +5 V in, regulated down to 3.3 V (LDO or buck)
- [x] 🧲 Decoupling caps on every VDD/VDDA pin (100 nF each + bulk)
- [x] 🎚️ VDDA filtering (ferrite bead + caps)
- [x] 🔁 Reset circuit (cap + button) on NRST
- [ ] 🥾 BOOT0 switch integrated
- [ ] 🐞 SWD debug header (SWDIO/PA13, SWCLK/PA14, NRST, 3V3, GND)
- [ ] 🔌 USB connector to the PC on PA11/PA12, with ESD protection
- [ ] 🖥️ Display connector (SPI and control lines)
- [ ] 💡 Status LED(s) and user button(s)
- [ ] ✔️ Pass ERC with no errors

### 🟩 PCB Layout
- [ ] 📏 Define the board outline and mounting holes
- [ ] 🔄 Push the schematic to the PCB (ECO)
- [ ] 🧩 Component placement (MCU in the center, decoupling caps close to the pins)
- [ ] 🧵 Routing (power first, then USB as a 90 Ω differential pair)
- [ ] 🌊 Ground pour on both layers, stitched with vias
- [ ] 🏷️ Silkscreen labels, logo and version number
- [ ] ✔️ Pass DRC with no errors

### 🏭 Manufacturing
- [ ] 🧾 Finalise the BOM with supplier part numbers
- [ ] 📤 Generate Gerbers, drill files and pick-and-place files
- [ ] 🛒 Order the PCBs (and parts)
- [ ] 🔧 Assemble the first prototype

### 🧪 Bring-up & Testing
- [ ] ⚡ Check the power rails (no shorts, 3.3 V present)
- [ ] 🐞 Connect over SWD and flash a blinky test
- [ ] 🔌 USB enumerates on the PC
- [ ] 🖥️ Display shows its first pixels
- [ ] 🤝 Talks to the [Snippet](https://github.com/Project-Snippet/Snippet) PC app
- [ ] 🚀 Snippet v1 complete!

---
