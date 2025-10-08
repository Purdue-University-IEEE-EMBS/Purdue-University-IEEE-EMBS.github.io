---
title: VOC Analyzer for Lung Cancer
parent: Projects
nav_order: 4
---

# VOC Analyzer for Lung Cancer

**Goal:** Detect volatile organic compounds (VOCs) in breath that indicate lung cancer.

## Summary
A handheld analyzer combines three sensor types:  
- **Metal-oxide (MOS)** for broad detection,  
- **Photoionization (PID)** for high sensitivity, and  
- **Nondispersive infrared (NDIR)** for gas-specific response.  

A built-in **pump and flow sensor** ensure consistent breath sampling, while a **Raspberry Pi + ESP32** system processes readings and sends them to a phone app for AI classification.  
The modular chamber design also allows future biosensor coatings for molecule-specific detection.

## Roles
- **Hardware:** Integrate sensors (MOS, PID, NDIR), flow system, and control electronics.  
- **Firmware:** Calibrate sensors, manage data collection, and control airflow via microcontrollers.  
- **AI/ML:** Build models to classify VOC patterns and predict lung cancer risk categories.  
- **Research/Biology:** Review literature on VOC biomarkers; map detected gases to clinical data.  
- **CAD/Design:** Create ergonomic, sealed housings for handheld use and replaceable mouthpieces.
