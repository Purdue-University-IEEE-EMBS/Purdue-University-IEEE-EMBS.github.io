---
title: Sleep Apnea Kit
parent: Projects
nav_order: 1
---

# Sleep Apnea Kit

**Goal:** Detect sleep apnea by monitoring oxygen levels, heart rate, breathing sounds, and brain activity during sleep.

## Summary
This kit integrates sensors such as a **SpO₂ module** for oxygen and pulse, **ECG electrodes** for heart rhythm, a **microphone** for breathing patterns, and **EEG electrodes** to detect brain arousals.  
An **Arduino Nano 33 BLE Sense** and **Raspberry Pi Pico W** coordinate data collection, while a **Real-Time Clock (RTC)** timestamps recordings overnight.  
A **LiPo battery** powers the system, logging results to an SD card for review.  
The final system synchronizes oxygen dips, heart rate changes, and EEG arousals to flag apnea events early.

## Roles
- **Hardware:** Assemble biosensors (EEG, ECG, SpO₂), wire circuits, integrate amplifiers and RTCs.  
- **Firmware:** Write code for data acquisition, synchronization, and SD card storage on Arduino/Pico.  
- **AI/ML:** Preprocess biosignal data, identify apnea patterns from combined physiological signals.  
- **Research/Biology:** Study physiological markers of sleep apnea and validate signal interpretation.  
- **CAD/Design:** Design enclosures for the headband, finger clip, and electronics housing.
