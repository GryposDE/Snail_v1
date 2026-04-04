# JDY-68A KiCad v9.0 Library & Schematic

## Files

| File | Description |
|------|-------------|
| `JDY-68A.kicad_sym` | Schematic symbol library |
| `JDY-68A.kicad_mod` | PCB footprint |
| `JDY-68A_application.kicad_sch` | Typical application schematic |
| `JDY-68A.kicad_pro` | KiCad project file |

---

## How to Use

### 1. Symbol Library
In KiCad 9 → **Preferences → Manage Symbol Libraries** → Add `JDY-68A.kicad_sym`.

### 2. Footprint Library
In KiCad 9 → **Preferences → Manage Footprint Libraries** → Add the folder containing `JDY-68A.kicad_mod`.

### 3. Open the Schematic
Open `JDY-68A.kicad_pro` in KiCad. The schematic (`JDY-68A_application.kicad_sch`) will load automatically.

---

## Pin Reference

| Pin | Name | Direction | Description |
|-----|------|-----------|-------------|
| 1 | VCC | Power in | 2.4V – 5.5V supply |
| 2–5 | NC | — | No connection |
| 6 | STAT/OUT3 | Output | BLE connection status (HIGH=connected) |
| 7 | GPIO2/OUT2 | Output | General purpose output |
| 8 | GPIO1/OUT1 | Output | General purpose output |
| 9 | ALED/OUT4 | Output | Advertising LED (500 ms blink) |
| **10** | **AUDIO** | **Output** | **Mono audio output → 8002 amplifier** |
| 11 | TXD | Output | UART TX (TTL, 9600 baud default) |
| 12 | RXD | Input | UART RX (TTL) |
| 13 | KEYIN | Input | AD key matrix input |
| 14 | NC | — | No connection |
| 15 | VCOM | Passive | Common reference (2µF cap to GND) |
| 16 | GND | Power in | Ground |

---

## Key Application Notes

- **Audio path**: Pin 10 (AUDIO) → 7.5kΩ resistors → NS8002 amplifier → speaker (up to 5W)
- **Decoupling**: Place 1µF cap close to VCC (pin 1); 2µF on VCOM (pin 15)
- **Crystal**: Use JDY-matched 24 MHz crystal for best RF performance
- **UART**: Default 9600 baud, 8N1. MCU TXD → module RXD, MCU RXD → module TXD
- **KEYIN resistor network** (all to GND, KEYIN pulled to VCC via 22kΩ):
  - Play/Pause: 0Ω | Previous: 9.1kΩ | Next: 3kΩ | Vol−: 51kΩ | Vol+: 24kΩ
- **Sleep**: Not supported — cut VCC to power down

---

## Footprint Notes

The footprint has:
- **8 SMD pads top row** (pads 1–8, 0.8 mm pitch)
- **8 SMD pads bottom row** (pads 17–24, 0.8 mm pitch)
- **6 through-hole pads left side** (OUT1, VCC, GND, TXD, RXD, OUT2 — 2.54 mm pitch)
- Antenna keep-out zone marked on F.Fab

Verify pad dimensions against your specific module sample before ordering PCBs.
