# Analog Signal Processor for ECG Monitoring with Adjustable Filtering

A complete analog front-end design for ECG signal acquisition, amplification, filtering, PCB fabrication, and hardware validation.  
This project focuses on extracting clean ECG signals from low-amplitude bio-signals while preserving diagnostically critical waveform features.

---

## Table of Contents
- Overview  
- Motivation  
- System Architecture  
- Circuit Design  
- Simulation and Analysis  
- PCB Design and Fabrication  
- Hardware Validation  
- Tools and Components  
- Repository Structure  
- Team and Contributions  
- References  
- Disclaimer  

---

## Overview

Electrocardiogram (ECG) signals typically lie in the range of **100 µV to a few millivolts**, making them highly vulnerable to noise sources such as motion artifacts, muscle interference, and power-line coupling.  
This project implements a **low-noise analog ECG signal processor** that amplifies and filters ECG signals using discrete analog building blocks.

The complete workflow includes:
- Analog circuit design and LTspice simulation
- Noise analysis using white noise injection
- Multi-stage analog filtering
- PCB layout, ERC/DRC verification, and Gerber generation
- Physical hardware testing and validation

---

## Motivation

Conventional ECG front-ends often rely on fixed or digitally assisted filtering. This project demonstrates how **purely analog signal processing** can be used to achieve clean ECG waveforms while preserving important cardiac features such as **P, QRS, and T complexes**, making it suitable for low-cost and portable applications.

---

## System Architecture

The ECG signal chain is structured as follows:
ECG Electrodes
↓
Instrumentation Amplifier
↓
Low-Pass Filter ─┐
├─→ Notch Filter → Output
Band-Pass Filter ┘


- Differential sensing improves immunity to common-mode noise  
- Parallel filtering preserves critical ECG frequency components  
- Notch filtering suppresses power-line interference  

---

## Circuit Design

### Instrumentation Amplifier
- Amplifies the differential ECG signal obtained from limb electrodes  
- Designed to handle microvolt-level input signals  
- High common-mode rejection ratio (CMRR) to suppress common-mode noise  

### Filtering Stages
- **Low-Pass Filter**  
  - Removes high-frequency noise and muscle artifacts  
- **Band-Pass Filter**  
  - Retains ECG-relevant frequency components required for cardiac analysis  
- **Notch Filter**  
  - Suppresses 50/60 Hz power-line interference  

All stages were designed, simulated, and validated in **LTspice** with emphasis on minimal waveform distortion and signal integrity.

---

## Simulation and Analysis

- Complete ECG signal chain simulated in LTspice  
- White noise added to emulate real-world interference conditions  
- Time-domain waveform analysis performed at multiple stages  
- Comparison of raw and filtered outputs carried out  

Key observations:
- Significant amplification of low-amplitude ECG signals  
- Clear preservation of P, QRS, and T waveform components  
- Effective suppression of noise and power-line interference  

---

## PCB Design and Fabrication

- Schematic capture followed by **Electrical Rule Check (ERC)**  
- PCB layout designed with analog signal integrity considerations  
- **Design Rule Check (DRC)** completed with no critical violations  
- Board dimensions approximately **100 mm × 100 mm**  
- Gerber and drill files generated for fabrication  
- 3D PCB rendering used to validate component placement and assembly  

---

## Hardware Validation

- PCB fabricated and assembled successfully  
- Instrumentation amplifier functionality verified in laboratory setup  
- End-to-end signal flow tested in real time  
- Hardware output closely matched simulated results  

---

## Tools and Components

### Software
- **LTspice** – Analog circuit simulation and noise analysis  
- **KiCad** – Schematic capture, PCB layout, ERC/DRC, Gerber generation  

### Hardware Components
- Operational Amplifiers: **TL082**, **LM741**  
- Precision resistors and capacitors  
- ECG electrodes for differential signal acquisition  

---

## Repository Structure

├── LTspice/
│ ├── Instrumentation_Amplifier.asc
│ ├── Filter_Stages.asc
│ └── Noise_Analysis.asc
│
├── PCB/
│ ├── Schematic.pdf
│ ├── PCB_Layout.kicad_pcb
│ ├── Gerbers/
│ └── 3D_Render/
│
├── Hardware_Testing/
│ ├── Lab_Demonstration
│ └── Observations.pdf
│
└── README.md



---

## Team and Contributions

**Team Name:** The Amplifires  

- **Bootla Sahasrith**  
  - Problem formulation  
  - Instrumentation amplifier design  
  - Circuit simulation and noise analysis  
  - PCB design, fabrication, and hardware validation  

- **Rupanjan Ghosh**  
  - Theory development  
  - System architecture and documentation  

- **Sonagiri Thoshith Kautilya**  
  - Filter design  
  - Circuit schematic development  

The project was collaboratively designed, reviewed, and validated by all team members.

---

## References

- LM741 Operational Amplifier Datasheet  
- TL082 Operational Amplifier Datasheet  
- Analog Devices ECG Front-End Documentation  

---

## Disclaimer

This project is intended **strictly for academic and educational purposes**.  
It is **not a certified medical device** and must not be used for clinical diagnosis or patient care.

