# phyphox:mini – PCB

KiCad project for the **phyphox:mini**, a small Bluetooth LE sensor board that
streams its measurements to the [phyphox](https://phyphox.org) app.

The design files were created with **KiCad 10**. Older KiCad versions cannot
open them.

## Hardware

| Part | Function |
|---|---|
| Nordic **nRF52832** (QFN48) | MCU with Bluetooth LE, internal DC/DC converter |
| ST **LSM6DSR** | accelerometer and gyroscope |
| Bosch **BMP580** | air pressure and temperature |
| TI **HDC1080** | relative humidity and temperature |
| Sensirion **STCC4** | CO₂ |
| Renesas/Adesto **AT25FF161A** | 16 Mbit (2 MB) SPI flash for data logging and firmware updates |
| 32 MHz and 32.768 kHz crystals | radio clock and low-power real-time clock |
| PCB antenna | 2.4 GHz, after TI application note SWRA117D |
| LED, test pads | status LED, programming and debugging (SWD) |

- 4-layer board, about 20 × 30 mm
- IMU and flash are connected via SPI; pressure, humidity and CO₂ sensors
  share one I²C bus.

## Files

| Path | Content |
|---|---|
| `Keyfob_2025_nrf52832.kicad_pro` | KiCad project |
| `Keyfob_2025_nrf52832.kicad_sch` | schematic |
| `Keyfob_2025_nrf52832.kicad_pcb` | board layout |
| `lib/` | project symbols (`*.kicad_sym`), footprints (`phyphox-footprints.pretty`) and 3D models (`3d/`) |

The project libraries are referenced relative to the project directory
(`sym-lib-table`, `fp-lib-table`), so the project opens without further setup.
