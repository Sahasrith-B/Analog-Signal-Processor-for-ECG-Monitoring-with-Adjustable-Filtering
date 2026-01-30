Overview

Electrocardiogram (ECG) signals are extremely low-amplitude bio-signals (typically 100 µV to a few mV) and are highly susceptible to motion artifacts, muscle noise, and power-line interference.
This project focuses on designing a robust analog ECG front-end that amplifies these weak signals while preserving medically significant waveform features such as P, QRS, and T complexes.

The complete system was designed, simulated, fabricated, and hardware-verified, covering the entire analog signal chain from electrodes to filtered output.

Project Objectives

Amplify low-level ECG signals using an instrumentation amplifier

Suppress noise while preserving diagnostic waveform integrity

Implement multi-stage analog filtering:

Low-pass

Band-pass

Notch (power-line interference)

Validate performance under white noise conditions

Design and fabricate a PCB with full ERC/DRC clearance

Perform real-time hardware testing

🧠 System Architecture

Signal Flow:

ECG Electrodes
     ↓
Instrumentation Amplifier
     ↓
Low-Pass Filter ─┐
                 ├─→ Notch Filter → Output
Band-Pass Filter ┘

Why this architecture?

ECG signals are differential in nature → instrumentation amplifier improves CMRR

Parallel filtering allows selective preservation of ECG frequency content

Notch filtering removes 50/60 Hz power-line interference without distorting waveform shape

🔧 Circuit Design Details
1️⃣ Instrumentation Amplifier

Differential amplification of ECG electrode signals

Designed to handle microvolt-level inputs

High CMRR to suppress common-mode noise

Acts as the low-noise front-end (LNA)

2️⃣ Filtering Stages

Low-Pass Filter

Removes high-frequency noise and muscle artifacts

Band-Pass Filter

Preserves ECG-relevant frequency components

Notch Filter

Eliminates power-line interference (50/60 Hz)

All filters were designed and verified in LTspice, with emphasis on minimal waveform distortion.

🧪 Simulation & Analysis

Full LTspice simulation of the complete signal chain

White noise injected to evaluate real-world robustness

Time-domain analysis to compare:

Raw ECG signal

Filtered output

Special attention given to:

QRS complex sharpness

P and T wave visibility

Observation:
The final filtered output significantly improves signal clarity while preserving all clinically important waveform features.

🧾 PCB Design & Fabrication

Schematic captured and verified with ERC

PCB layout designed with:

Proper grounding

Analog signal integrity considerations

DRC-clean board

Board dimensions approximately 100 mm × 100 mm

Generated:

Gerber files

Drill files

Manufacturing outputs

3D PCB render used to validate component placement and assembly feasibility

🔌 Hardware Validation

PCB fabricated and assembled

Instrumentation amplifier behavior verified in lab

End-to-end signal flow tested in real time

Hardware results matched simulated performance closely

🧰 Tools & Components Used
Software

LTspice – circuit simulation and noise analysis

KiCad – schematic capture, PCB layout, ERC/DRC, Gerber generation

Hardware

Operational Amplifiers:

TL082

LM741

Passive components:

Precision resistors

Capacitors

ECG electrodes (arm-to-arm measurement)

📁 Repository Structure
├── LTspice/
│   ├── Instrumentation_Amplifier.asc
│   ├── Filters.asc
│   └── Noise_Analysis.asc
│
├── PCB/
│   ├── Schematic.pdf
│   ├── PCB_Layout.kicad_pcb
│   ├── Gerbers/
│   └── 3D_Render/
│
├── Hardware_Testing/
│   ├── Lab_Demo_Images
│   └── Observations.pdf
│
└── README.md

👥 Team & Contributions

Team Name: The Amplifires

Sahasrith Bootla

Problem formulation

Instrumentation amplifier design

Circuit simulation

PCB design & fabrication

Hardware validation

Rupanjan Ghosh

Theory and signal analysis

System architecture and documentation

Sonagiri Thoshith Kautilya

Filter design

Schematic development

The system design and debugging were carried out collaboratively.

📚 References

LM741 Operational Amplifier Datasheet

TL082 Operational Amplifier Datasheet

Analog Devices ECG Front-End References (AD823x series)

🚀 Future Improvements

Replace discrete op-amps with a dedicated ECG AFE IC

Add right-leg drive (RLD) for improved common-mode rejection

Integrate ADC + digital post-processing

Miniaturize PCB for wearable applications

⚠️ Disclaimer

This project is intended for educational and research purposes only and is not a certified medical device.
