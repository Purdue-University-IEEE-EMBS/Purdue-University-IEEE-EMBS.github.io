---
title: Hardware
parent: Onboarding
nav_order: 4
---

## **Hardware Onboarding**

---

### **Purpose of the Hardware Role**
Hardware members are responsible for building and testing the physical electronic circuits that connect sensors, microcontrollers, and medical prototypes. Your work ensures the data is accurate, safe, and reliable before firmware, AI/ML, or CAD teams can build on it.

---

### **Why This is Needed**
- Ensures all hardware members understand the electrical foundations before designing medical devices.
- Builds confidence in safe wiring and measurement.
- Guarantees that PCBs and circuits you design for EMBS are reliable, safe, and functional.

---

### **Onboarding Process**
1. **Learn** → Review the Hardware learning resources
2. **Learning Check** → Complete the Hardware Knowledge Check using the provided Equations Sheet and learning resources.
3. **Assignment** → Follow the KiCad tutorial to design a pulse oximeter PCB. 
    - Deliverables:
        - Schematic and PCB files.
        - Generated Gerber files (zipped).
        - Submit via the Hardware KiCad Submission Google Form.
4. **Demo** → Build and test a button-activated LED circuit
5. **Review** → A senior officer will review your assignment, knowledge check, and demo.
6. **Discord Role Update** → Once approved your role will be updated to hardware in discord.

***

### **Skills to Learn**
**Circuit Basics:**
- Ohm’s Law (V = IR)
- Voltage dividers & resistor networks
- Filtering with capacitors/RC circuits
- Pull-up and pull-down resistors

**Sensors & Signals**
- Analog vs. digital signals
- Signal noise, shielding, grounding basics
- Biosensors: PPG (heart rate), microphone (stethoscope), thermistor (temperature), IMU/accelerometer

**Prototyping**
- Breadboarding circuits correctly
- Soldering through-hole & basic SMD parts
- Using multimeters for continuity/voltage/current
- Using an oscilloscope to visualize signals

**Safety**
- Always use isolated power supplies (no direct wall current).
- Never allow current paths through the body.
- Follow Purdue lab safety protocols for soldering and electronics.

***

### **Learning Resources**
Complete these in order:

**Fundamentals**
- [**Circuits**](https://www.allaboutcircuits.com/textbook/direct-current/chpt-1/voltage-current-practical-circuit/)
- [**Ohm’s Law**](https://www.fluke.com/en-us/learn/blog/electrical/what-is-ohms-law?srsltid=AfmBOoqQZKO_QN6PlmaolgXwU_aWvTVTZV7aWYkAI-XkT54i1yoCv5PH)
- [**Kirchhoff’s Law**](https://www.electronics-tutorials.ws/dccircuits/kirchhoffs-voltage-law.html)
- [**Voltage Dividers**](https://www.allaboutcircuits.com/tools/voltage-divider-calculator/)
- [**Capacitors**](https://youtu.be/rbCXKhhzBN0?si=8iG7cCKgxO0jfTx6) 
- [**High Pass Filter**](https://www.electronics-tutorials.ws/filter/filter_3.html)
- [**Low Pass Filter**](https://www.electronics-tutorials.ws/filter/filter_5.html)
- [**Operational Amplifier**](https://youtu.be/idJEMYhrIfs?si=HHGSDWnKEFl7rsTN)
- [**Safe Circuit Design**](https://www.allaboutcircuits.com/textbook/direct-current/chpt-3/safe-circuit-design/)
- [**Helpful Tool: Multisim Circuit Simulator**](https://www.multisim.com/get-started/)

**Hands-On Skills**
- [**Multimeter Basics**](https://docs.arduino.cc/learn/electronics/multimeter-basics/)
- [**Oscilloscope Basics**](https://www.keysight.com/us/en/assets/7018-01761/application-notes/5989-8064.pdf)
- [**Soldering Basics**](https://www.instructables.com/A-Comprehensive-Guide-to-Soldering-Techniques-Tool/)

**PCB Design**
- [**KiCad Official Getting Started Guide**](https://docs.kicad.org/7.0/en/getting_started_in_kicad/getting_started_in_kicad.html)
- [**KiCad Tutorial**](https://www.youtube.com/watch?v=vLnu21fS22s&list=PLUOaI24LpvQPls1Ru_qECJrENwzD7XImd)

**Our Microcontroller**
- [**Arduino Nano 33 BLE Sense Rev2**](https://docs.arduino.cc/hardware/nano-33-ble-sense-rev2/#features)

***

### **Learning Check**
Before moving to the assignment, complete the knowledge check with the resources opened to refer to as needed:
- [**Knowledge Check**](https://docs.google.com/forms/d/e/1FAIpQLSeYqhCYm9LP5T_XrsGYgARnJlrhMhwYBFwkG8uAnVSPDxzsOw/viewform?usp=header)
- [**Equations Sheet**](https://purdue-university-ieee-embs.github.io/assets/Hardware_Equations_Sheet.pdf)

***

### **Assignment**
By the end of this assignment, you’ll know how to:
- Install and set up KiCad (industry-standard PCB design software).
- Build a schematic in KiCad
- Generate and submit your first set of Gerber files (the files PCB manufacturers use).
This will give you hands-on practice with tools and concepts you’ll use in real EMBS projects.

**Step 1: Install the Tools**
1. [**Download KiCad**](https://www.kicad.org/download/) (latest stable release)

**Step 2: Background Concepts**
Before you start, here’s what to keep in mind:
- Ohm’s Law & KVL:
    - Used to size resistors for LEDs, voltage dividers, and biasing.
- RC Filters:
    - A resistor + capacitor can make a low-pass filter (smooth out high-frequency noise) or a high-pass filter (remove slow baseline drift).
- Signal Acquisition in Biomedical Circuits:
    - Raw signals (like heartbeats from the MAX30102 sensor) are very weak.
    - We add filter networks (RC) to clean them up before amplification or digitization
    - This is why you’ll see resistors and capacitors around the sensor input/output in the tutorial.

**Step 3: Follow the Tutorial**
- Watch and follow along with the [**YouTube tutorial**](https://www.youtube.com/watch?v=vLnu21fS22s&list=PLUOaI24LpvQPls1Ru_qECJrENwzD7XImd) that walks through designing a pulse oximeter PCB in KiCad.
- Components used in the design:
    - SSD1306 OLED display (for output).
    - MAX30102 pulse oximeter (for heart rate/SpO2 sensing).
    - Arduino Nano (for processing).
As you follow, make sure to replicate the schematic and PCB footprints in KiCad. Feel free to replicate or design your own layout for the PCB.

**Step 4: Deliverable**
- When you finish your board:
    1. Generate Gerber files in KiCad (File → Plot → select Gerber) and zip into a folder
        - Here's a [**link**](https://jlcpcb.com/help/article/how-to-generate-gerber-and-drill-files-in-kicad-7) to how to generate gerbers compliant with JLCPCB, the manufacturer we will use.
        - Once your files are generated you can upload them to JLCPCB to review the layers and more details.
    2. Zip your project files (Schematic and PCB files)
    3. Zip gerbers and project files into one folder. Format:
        - Main folder
            - gerbers.zip
            - projectfiles.zip
    4. Submit your zipped files via the Google Form:
        - [**Hardware KiCad Submission**](https://docs.google.com/forms/d/e/1FAIpQLScT3uqwATZoLIDZJTKLburehK82ub0THXSZ8IRxTgd-FmNdaQ/viewform?usp=header)_
 
***

### **Demo**
**Task:** Design and test button activated LED

- **Calculate** the resistor value to provide the correct amount of current to the LED (look for the forward current in this [datasheet](https://cdn.sparkfun.com/assets/e/c/e/c/5/COM-09590-YSL-R531R3D-D2.pdf))

        ![Circuit](/assets/images/circuit.webp)

- **Design:**
    - Draw the schematic and test functionality in **Multisim** 

- **Prototype:**
    - Build the circuit on a breadboard.
    - Do **NOT** turn on the power supply.

        ![Breadboard](/assets/images/breadboard.webp)

- **Deliverable:**
    - Once fully built, confirm the circuit with an officer before turning on the power supply.
    - Demonstrate the button turning on the LED.