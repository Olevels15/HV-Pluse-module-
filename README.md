# HV-Pluse-module-

HV Pulse module for the VPS prototype transmit path.

## Current Registered Drawing Package

The current review package is the **2026-07-23 HV Pulser 180 Vpp / PCB8 package**, registered in:

`docs/HV_Pulser_Drawing_Register.md`

Supplied files for this package:

- `PCB_PCB8_2026-07-23.pdf`
- `Main Altium_HV Pulse lite.tbo_2026-07-23.zip`

The supplied PDF identifies the board as:

`180VPP DRIVER HV PULSER REV 2`

Visible interface and review signals include:

- `FPGA_SIG_ENABLE`
- `PULSE_P`
- `PULSE_N`
- `DAMP_P`
- `DAMP_N`
- `TX_MON_D_TO_FPGA`
- `TX_MON_A`
- `+3.3V SUPPLY`
- `HV_+90V`
- `HV_-90V`
- `GND_N`
- `GND`
- `NET TIE GND`

## Engineering Status

This repository currently records the drawing package for engineering review. The binary PDF and Altium ZIP should be uploaded as controlled repository files or GitHub release assets before this repository is treated as holding the complete design package.

Do not treat this pulser as safe for bench energisation until the following checks are completed and recorded:

1. schematic-to-PCB comparison;
2. 13-pin connector pinout and harness check;
3. `GND_N`, logic `GND`, shield/chassis and VPS analogue/digital ground return strategy;
4. HV probe/discharge/test-load procedure;
5. attenuation and comparator threshold check for `TX_MON_D_TO_FPGA`;
6. decision on whether `TX_MON_A` is test-only or routed as an analogue reference/monitor;
7. FPGA default-safe state for `FPGA_SIG_ENABLE`, `PULSE_P`, `PULSE_N`, `DAMP_P` and `DAMP_N`.
