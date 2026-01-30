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

