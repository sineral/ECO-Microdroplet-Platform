# ECO-Microdroplet-Platform

**An automated multichannel microdroplet platform for chemical reaction screening and optimization.**

Developed at Zhejiang University, this platform integrates LabVIEW-based experimental automation, reaction control, online LC–MS analysis, and algorithm-assisted optimization.

**Author:** Xian Zheng | Zhejiang University  
**Publication:** Manuscript in preparation

## Features

- Automated reagent preparation and microdroplet handling
- Six-channel parallel reaction control
- Temperature, irradiation, pressure, and oscillation control
- Automated product transfer, cleaning, and LC–MS integration
- Experiment scheduling and execution logging
- WebService interface for algorithm-driven closed-loop optimization

## Repository Structure

```text
ECO-Microdroplet-Platform/
├── automated-microdroplet-platform/   # LabVIEW control software
│   ├── automated-microdroplet-platform.lvproj
│   ├── main interface.vi
│   ├── operation/
│   ├── worker/
│   ├── subVI/
│   └── shared variables/
├── WebService/                        # Algorithm integration
├── Data/
│   └── Platform data/
│       └── Experiment List.txt        # Experimental task list
└── recommend_noTMG_mixedBO.py         # Bayesian optimization
```

## Getting Started

**Requirements:** LabVIEW 2024 Q3, compatible instrument drivers, and the corresponding experimental hardware.

1. Open `automated-microdroplet-platform.lvproj` in LabVIEW.
2. Update local log directories, serial ports, IP addresses, and instrument communication settings in the relevant subVIs.
3. Configure experiments in `Data/Platform data/Experiment List.txt`.
4. Open `main interface.vi`, configure the operating parameters, and enable the required reaction channels.
5. Run the program to execute the experimental task list automatically.

**Important:** Hardware communication settings and file paths are specific to the original experimental setup and must be configured before use.

## Closed-Loop Optimization

The `WebService` module enables communication between the experimental platform and external optimization algorithms.

- `GetStatus.vi` — Retrieve platform status.
- `next_conditions.vi` — Exchange recommended experimental conditions.

The optional `recommend_noTMG_mixedBO.py` script implements mixed-variable Bayesian optimization using BoTorch. Python dependencies include PyTorch, GPyTorch, BoTorch, NumPy, and pandas.

## License

License information will be provided upon release.

## Citation

Related publication: *Manuscript in preparation.*

Please cite the associated publication when it becomes available.
