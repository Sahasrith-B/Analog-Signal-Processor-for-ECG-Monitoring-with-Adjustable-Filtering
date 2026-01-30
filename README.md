# Analog Signal Processor for ECG Monitoring with Adjustable Filtering

This repository presents the design and validation of an analog front-end for ECG signal acquisition. The system amplifies low-amplitude ECG signals and suppresses common noise sources while preserving diagnostically significant waveform features.

---

## Overview

ECG signals typically range from 100 µV to a few millivolts and are highly susceptible to motion artifacts, muscle noise, and power-line interference. This project implements a low-noise, fully analog ECG signal processor using discrete components.

The project includes:
- LTspice-based circuit design and simulation  
- Noise robustness evaluation using white noise injection  
- Multi-stage analog filtering  
- PCB design, ERC/DRC verification, and fabrication  
- Hardware testing and validation  

---

## Design Objectives

- Amplify microvolt-level differential ECG signals  
- Suppress motion artifacts and power-line interference  
- Preserve P, QRS, and T waveform components  
- Demonstrate a low-cost analog ECG front-end  

---

## System Architecture

Differential ECG signals acquired from electrodes are amplified using an instrumentation amplifier and subsequently processed through dedicated filtering stages.

The signal-processing chain consists of:
- Instrumentation amplification  
- Low-pass filtering for high-frequency noise suppression  
- Band-pass filtering to retain ECG-relevant frequencies  
- Notch filtering to suppress power-line interference  

---

## Circuit Design

### Instrumentation Amplifier
- Differential amplification of ECG signals  
- High common-mode rejection ratio (CMRR)  

### Filtering Stages
- **Low-Pass Filter** – Attenuates high-frequency noise  
- **Band-Pass Filter** – Preserves ECG-relevant frequency content  
- **Notch Filter** – Suppresses 50/60 Hz interference  

All stages were designed and verified in LTspice with emphasis on signal integrity.

---

## Simulation and Analysis

- Complete ECG signal chain simulated in LTspice  
- White noise injected to emulate real-world interference  
- Time-domain analysis performed across stages  

Results show effective amplification, noise suppression, and clear preservation of ECG waveform features.

---

## PCB Design and Hardware Validation

- Schematic capture with ERC verification  
- PCB layout completed with DRC compliance  
- Board size approximately 100 mm × 100 mm  
- Gerber files generated and fabricated  
- Hardware testing confirmed close agreement with simulation results  

---

## Tools and Components

**Software:** LTspice, KiCad  
**Hardware:** TL082, LM741 op-amps, precision passive components, ECG electrodes  

---

## Repository Structure

- `LTspice/` – Circuit simulations and noise analysis  
- `PCB/` – Schematic, layout, Gerbers, and 3D render  
- `Hardware_Testing/` – Lab demonstrations and observations  


---


## Disclaimer

This project is intended solely for academic and educational purposes and is not a certified medical device.
