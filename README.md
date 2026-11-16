# Battery Pack Monitor with EKF State-of-Charge Estimation

**Status: in progress.** This repository is being built; nothing here is a finished result yet.

## Goal

A 4-cell Li-ion pack monitor on STM32: cell voltages, pack current and temperature streamed over CAN; over/under-voltage and over-temperature protection driving a cutoff MOSFET; and state-of-charge estimation with an extended Kalman filter on a 2-RC cell model, compared against coulomb counting.

## Layout

```
firmware/afe/             # Cell voltage, current and temperature sampling.
firmware/protection/      # OV/UV/OT limits, cutoff MOSFET, fault codes.
firmware/can/             # Telemetry frames.
estimation/model/         # 2-RC equivalent-circuit cell model and parameter fitting.
estimation/ekf/           # EKF prototype (Python) and C port.
estimation/notebooks/     # Analysis notebooks.
data/                     # Discharge and pulse test logs (format described here).
hardware/                 # Schematic, BOM and safety notes (low-voltage 4S pack only).
docs/                     # Design and results.
```

## Plan

- [ ] Sensing + CAN telemetry
- [ ] Protection and cutoff
- [ ] Cell characterisation (pulse tests)
- [ ] 2-RC model fit
- [ ] EKF prototype in Python
- [ ] EKF port to firmware
- [ ] SoC accuracy vs coulomb counting
- [ ] Write-up
