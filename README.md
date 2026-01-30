# Analog Signal Processor for ECG Monitoring with Adjustable Filtering

This repository presents the design, simulation, fabrication, and validation of an analog front-end for electrocardiogram (ECG) signal acquisition. The system is designed to amplify low-amplitude ECG signals and suppress common noise sources while preserving diagnostically significant waveform features.

---

## Overview

Electrocardiogram (ECG) signals are low-amplitude bio-signals, typically ranging from 100 µV to a few millivolts. These signals are highly susceptible to interference from motion artifacts, muscle activity, and power-line coupling. Effective analog front-end design is therefore critical to ensure signal integrity prior to digitization or further processing.

This project implements a complete analog ECG signal processor using discrete components. The work spans the full hardware development lifecycle, including circuit design, simulation, printed circuit board (PCB) fabrication, and experimental validation.

The scope of the project includes:
- Analog circuit design and LTspice simulation
- Noise robustness evaluation using white noise injection
- Multi-stage analog filtering
- PCB schematic capture, layout, and rule verification
- Gerber generation and board fabrication
- Hardware testing and performance validation

---

## Design Objectives

- Amplify microvolt-level differential ECG signals with high common-mode rejection
- Suppress motion artifacts, muscle noise, and power-line interference
- Preserve critical ECG waveform components (P, QRS, and T complexes)
- Demonstrate a low-cost, fully analog ECG front-end suitable for portable systems

---

## System Architecture

The ECG front-end follows a sequential analog signal-processing chain. Differential ECG signals acquired from electrodes are first amplified using an instrumentation amplifier. The amplified signal is subsequently processed through dedicated filtering stages to suppress noise while preserving diagnostically relevant frequency components.

The signal-processing stages include:
- Instrumentation amplification for low-level differential ECG signals
- Low-pass filtering to attenuate high-frequency noise and muscle artifacts
- Band-pass filtering to retain ECG-relevant frequency content
- Notch filtering to suppress power-line interference

This architecture ensures robust noise rejection while maintaining waveform fidelity.

---

## Circuit Design

### Instrumentation Amplifier

- Differential amplification of ECG electrode signals
- Designed to operate with microvolt-level input amplitudes
- High common-mode rejection ratio (CMRR) to mitigate common-mode noise

### Filtering Stages

- **Low-Pass Filter**  
  Attenuates high-frequency noise and muscle artifacts.

- **Band-Pass Filter**  
  Preserves frequency components relevant to ECG waveform analysis.

- **Notch Filter**  
  Suppresses power-line interference at 50/60 Hz.

All circuit blocks were designed and validated in LTspice with emphasis on stability, signal integrity, and minimal waveform distortion.

---

## Simulation and Analysis

- Complete ECG signal chain simulated using LTspice
- White noise injected to emulate real-world interference conditions
- Time-domain analysis performed at multiple nodes
- Comparison of raw and filtered outputs conducted

Simulation results demonstrate:
- Significant amplification of low-amplitude ECG signals
- Effective noise suppression across filtering stages
- Clear preservation of P, QRS, and T waveform components

---

## PCB Design and Fabrication

- Schematic capture followed by Electrical Rule Check (ERC)
- PCB layout designed with analog signal integrity considerations
- Design Rule Check (DRC) completed without critical violations
- Board dimensions approximately 100 mm × 100 mm
- Gerber and drill files generated for fabrication
- 3D PCB rendering used to verify component placement and assembly feasibility

---

## Hardware Validation

- PCB fabricated and assembled successfully
- Instrumentation amplifier functionality verified in laboratory testing
- End-to-end signal flow validated under real-time conditions
- Hardware measurements closely matched simulation results

---

## Tools and Components

### Software Tools
- LTspice – Analog circuit simulation and noise analysis
- KiCad – Schematic capture, PCB layout, ERC/DRC verification, and Gerber generation

### Hardware Components
- Operational amplifiers: TL082, LM741
- Precision resistors and capacitors
- ECG electrodes for differential signal acquisition

---

## Repository Structure

- `LTspice/`  
  - `Instrumentation_Amplifier.asc` – Instrumentation amplifier simulation  
  - `Filter_Stages.asc` – Low-pass, band-pass, and notch filter simulations  
  - `Noise_Analysis.asc` – White noise robustness analysis  

- `PCB/`  
  - `Schematic.pdf` – Complete circuit schematic  
  - `PCB_Layout.kicad_pcb` – PCB layout file  
  - `Gerbers/` – Manufacturing-ready Gerber files  
  - `3D_Render/` – 3D PCB visualization  

- `Hardware_Testing/`  
  - `Lab_Demonstration/` – Hardware testing and measurements  
  - `Observations.pdf` – Experimental results and observations  

- `README.md` – Project documentation

---

## Team and Contributions

**Team Name:** The Amplifires

- **Bootla Sahasrith**  
  Circuit design, simulation, PCB layout, fabrication, and hardware validation

- **Rupanjan Ghosh**  
  System architecture, theoretical analysis, and documentation

- **Sonagiri Thoshith Kautilya**  
  Filter design and circuit schematic development

The project was jointly designed, reviewed, and validated by all team members.

---

## References

- LM741 Operational Amplifier Datasheet  
- TL082 Operational Amplifier Datasheet  
- Analog Devices ECG Front-End Application Notes  

---

## Disclaimer

This project is intended solely for academic and educational purposes.  
It is not a certified medical device and must not be used for clinical diagnosis or patient care.
