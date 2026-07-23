# HV Pulser Drawing Register

## Current Design Package — 2026-07-23

**Status:** Current drawing package registered for review. Binary PDF/Altium files must be uploaded to the repository or release assets as controlled files before the package is treated as a complete manufacturing baseline.

### Source Files Supplied

| Item | Supplied File | SHA-256 | Notes |
| --- | --- | --- | --- |
| PCB drawing / placement / BOM PDF | `PCB_PCB8_2026-07-23.pdf` | `a0ff880b8ab86bc6d5b74f4ca02ccef10cf3cf4969ea7fae9ee8cd78a4223544` | Seven-page PDF containing PCB placement views, BOM tables and board artwork for `180VPP DRIVER HV PULSER REV 2`. |
| Altium source package | `Main Altium_HV Pulse lite.tbo_2026-07-23.zip` | `3be42bfff04d3ce319b10c589df6f2c899d9eff3d13cc7cbad291f94c9ace54b` | Altium package containing `P1.schdoc` and `PCB8.pcbdoc` under the `HV Pluser 180Vpp` project path. |

### Altium Package Contents

```text
HV Pulse lite.tbo/
HV Pulse lite.tbo/HV Pluser 180Vpp/
HV Pulse lite.tbo/HV Pluser 180Vpp/HV Pulser 180Vpp/
HV Pulse lite.tbo/HV Pluser 180Vpp/HV Pulser 180Vpp/P1.schdoc
HV Pulse lite.tbo/HV Pluser 180Vpp/PCB8.pcbdoc
```

### Drawing / PCB Observations from Supplied PDF

The July 2026 PCB drawing identifies the board as:

`180VPP DRIVER HV PULSER REV 2`

Visible functional labels include:

- `TX_MON_D_TO_FPGA`
- `TX_MON_A`
- `PULSE_P`
- `PULSE_N`
- `DAMP_P`
- `DAMP_N`
- `FPGA_SIG_ENABLE`
- `+3.3V SUPPLY`
- `HV_+90V`
- `HV_-90V`
- `GND_N`
- multiple `GND` returns
- `NET TIE GND`
- matching selector positions for bypass, 10 uH, 22 uH, 33 uH and bypass-all options.

### BOM / Component Evidence from Supplied PDF

Key components shown in the PDF BOM include:

| Function | Designator | Component / Value |
| --- | --- | --- |
| 13-pin VPS carrier connector | `CN2` | `XD-2510-13A` |
| HV pulser IC | `U8` | `HV7360GA-G` |
| Digital comparator / monitor output | `U5` | `TLV3501AIDBVR` |
| ±90 V supply connector | `U9` | `KF301-5.0-3P` |
| 3.3 V to ~10 V boost regulator | `U10` | `TPS61041DBVR` |
| Output / RF connector | `U12` | `4GHz` RF connector |
| Logic supply protection | `F1` | `SMD1206P200TF` |
| Ferrite bead | `FB3` | `BLM21PG600SN1D` |
| Matching selector header | `H1` | `PZ254V-12-10P` |
| Matching inductors | `L1`, `L2`, `L3` | `10uH`, `22uH`, `33uH` |

### Engineering Control Notes

1. Treat this as the current HV pulser drawing package for review, replacing earlier 2026-07-10 HV pulser drawing references once the binary files are uploaded to the repository or GitHub release assets.
2. `TX_MON_D_TO_FPGA` remains a digital pulse-monitor / timing-feedback signal unless a separate analogue coherent reference path is explicitly selected and verified.
3. `TX_MON_A` is available as an analogue monitor/test-point function and should not be allowed to wander through the noisy pulser region.
4. `GND_N`, `GND`, `GND_SHIELD`, connector shield and any chassis/protective-earth treatment require a controlled return-path/star decision before energising.
5. Interleaved signal returns at `CN2` shall reduce loop area and crosstalk, but HV pulse current must not return through the low-noise VPS receive/ADC analogue ground path.
6. The matching selector must be configured with one intended option fitted/selected at a time unless a specific bypass-all test mode is deliberately recorded.
7. This package is not yet a released manufacturing or bench-energisation baseline until schematic-to-PCB, BOM, connector pinout, grounding, protection and test-equipment safety checks are completed.

### Required Repository File Promotion

Upload or attach the binary files as controlled repository assets or release assets:

- `drawings/PCB_PCB8_2026-07-23.pdf`
- `altium/Main_Altium_HV_Pulse_lite_tbo_2026-07-23.zip`

After promotion, update this register with their repository paths and mark the package status as `Stored in repository`.
