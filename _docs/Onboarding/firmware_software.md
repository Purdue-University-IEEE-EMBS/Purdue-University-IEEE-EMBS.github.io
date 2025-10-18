---
title: Firmware/Softare
parent: Onboarding
nav_order: 1
---

## **Frimware / Software Onboarding**

***

### **Onboarding Steps**

1. **Learn** → Review the Firmware learning resources
2. **Run Example** → Run the DigitalReadSerial.ino example
3. **Learning Check** → Complete the learning check
4. **Assignment** → Small firmware project for debuging and demoing a the thermistor
5. **Demo** → Show your working thermistor circuit to an officer/mentor for verification
6. **Review** → An officer will check your code for correctness and readability
7. **Role Update** → You’re marked as 'Firmware Verified' in the onboarding tracker and gain access to the firmware-team channel

***

### **Purpose of Firmware Role**

Firmware engineers in EMBS are responsible for bringing the hardware to life, and without firmware, the medical prototype cannot collect or send any meaningful data. Firmware engineers are responsible for writing and debuging the code that will...
- Read data from sensors (temperature, microphone, accelerometer, etc.)
- Process the data in real time (filtering, feature extraction, etc.)
- Communicate with other devices or modules (via Bluetooth, UART, SPI, I²C)
- Provide the “glue” between hardware, AI/ML models, and project logic.

***

### **Prerequisites To Onboarding**

**Background Skills:**
- Familiarity with basic [**C**](https://www.w3schools.com/c/), [**C++**](https://www.w3schools.com/cpp/cpp_intro.asp), or [**Python**](https://www.w3schools.com/python/default.asp) (variables, loops, functions).
- Comfort and understanding of how to use a text editor / IDE.

**Tools Needed:**
- Arduino IDE
    - Download & install → [**Arduino IDE**](https://www.arduino.cc/en/software/)
        - Add Arduino BLE Library (needed for Nano 33 BLE Sense).
- Wokwi Simulator (Optional, This is a handy tool for testing code)
    - [**Wokwi Arduino Simulator**](https://wokwi.com/arduino) → lets you test simple sketches online without hardware.
- Git & GitHub
    - Install Git → [**Git Download**](https://git-scm.com/downloads)
    - Create a GitHub account → [**Join GitHub**](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://github.com/signup&ved=2ahUKEwj_0Lbl4auQAxVGliYFHcNqLW0QjBB6BAgTEAE&usg=AOvVaw0a6qEmIZVdziwPUb-hFApr)
        - Work through [**Hello World GitHub Guide**](https://docs.github.com/en/get-started/start-your-journey/hello-world) if not familiar with GitHub ***(Optional)***

***

### **Skills You Will Learn Through Onboarding**
This first portion of onboarding is meant to build some knowledge and skills that will becaome very useful when working on our projects as a firmware team member. As such, please take some time to look into the resources and learn skills in:

**Programming Foundations**

- Write clean and readable C++/Arduino code.
- Understand variables, data types, loops, and conditionals.
- Use functions to structure code.

**Embedded Systems Concepts**

- Pin modes and digital/analog I/O.
- Using Serial Monitor for debugging.
- Reading sensor values and processing them.
- Using timers and delays responsibly.

**Hardware Communication**
- I²C and SPI basics (reading from sensors, sending to displays).
- UART/Serial for debugging or device-to-device communication.
- Bluetooth Low Energy (BLE) for wireless communication.

**Software Tools**

- Git basics: clone, commit, push, pull.
- Arduino libraries: how to find, install, and use them.
- Wokwi/Arduino simulator debugging.

***

### **Learning Resources**
**Arduino Programming Basics**

- [**Arduino Language Reference**](https://www.arduino.cc/reference/en/)
    - Functions
        - setup()
        - loop()
        - custom functions
    - Variables/Data types
        - int
        - float
        - bool
        - String.
    - Constants:
        - HIGH/LOW
        - INPUT/OUTPUT
        - LED_BUILTIN.
    - Operators:
        - arithmetic ```(+, -, *, /, %)```
        - boolean ```(&&, ||, !)```
- [**Arduino IDE Guide**](https://docs.arduino.cc/learn/starting-guide/the-arduino-software-ide/)

**Debugging & Timing**

- [**Serial Communication Docs**](https://www.arduino.cc/reference/en/language/functions/communication/serial/)
- [**Timing Functions**](https://www.electronicwings.com/arduino/basic-functions-related-to-time-and-interrupts-in-arduino)
- [**Blink Without Delay Tutorial**](https://www.arduino.cc/en/Tutorial/BuiltInExamples/BlinkWithoutDelay)

**Hardware Communication**

- [**I²C Basic**](https://docs.arduino.cc/learn/communication/wire)
- [**SPI Basics**](https://docs.arduino.cc/learn/communication/spi)
- [**UART Basics**](https://www.arduino.cc/en/Reference/Serial)
- [**ArduinoBLE Library**](https://www.arduino.cc/en/Reference/ArduinoBLE)

**Software Tools**

- [**Arduino Project Hub**](https://docs.arduino.cc/tutorials/nano-33-ble-sense-rev2/community-projects/)

***

### **Run An Example**
1. Connect pre-constructed arduino to computer using the Arduino IDE
2. Select the COM port where the Arduino BLE is located
3. Load an example into the sketch editor
    ![Load Example](/assets/images/firmware-load-example.webp)
    - Go to File -> Examples -> Basics ->DigitalReadSerial.ino
4. Ask for the Firmware Arduino Example Circuit from the chair and connect the floating wire to the correct digital pin (D2) using the the [**Arduino BLE Sense Pinout**](https://docs.arduino.cc/resources/pinouts/ABX00069-full-pinout.pdf)
    - If not in person complete next step using [**wokwi**](https://wokwi.com/projects/442845427932889089)
        - All you have to do is connect the correct digital pin to the button.
5. Upload the code to the arduino
6. Go to Tools -> Serial Monitor to open the serial monitor.
![Serial Monitor](/assets/images/firmware-serial-monitor.webp)
7. Push the button on the breadboard.
8. Take a screenshot of the entire screen with the sketch, serial monitor, and time in view.

***

### **Learning Check**
Before moving on to the demo task, please complete our knowledge check to demonstrate a basic understanding of some of the resources we will be using, and submit a screenshot of the example running. Both of these tasks can be done through through our google form.

<div style="text-align: center; margin: 20px 0;">
  <a href="https://docs.google.com/forms/d/e/1FAIpQLSeBFK-sHQQiTi4i0fNUUKdbWnyLrhtSDi8835VWrUBRKBl7SA/viewform?usp=preview" 
     style="
       display: inline-block; 
       padding: 12px 24px; 
       border: 2px solid #6f2dbd; 
       border-radius: 8px; 
       background-color: #f0f8ff; 
       color: #6f2dbd; 
       text-decoration: none; 
       font-weight: bold;"
    onmouseover="this.style.backgroundColor='#975ddaff'; this.style.color='#ffffff';"
    onmouseout="this.style.backgroundColor='#f0f8ff'; this.style.color='#975ddaff';">
    Firmware Learning Check
  </a>
</div>

***

### **Demo Task**
1. Navigate to the Firmware folder in the drive
2. Download the thermistor_demo.ino file
<div style="text-align: center; margin: 20px 0;">
  <a href="https://drive.google.com/file/d/1hUi7WCnmCZuaKMKo60Pk5XF6yeI7vM5z/view?usp=drive_link" 
     style="
       display: inline-block; 
       padding: 12px 24px; 
       border: 2px solid #6f2dbd; 
       border-radius: 8px; 
       background-color: #f0f8ff; 
       color: #6f2dbd; 
       text-decoration: none; 
       font-weight: bold;"
    onmouseover="this.style.backgroundColor='#975ddaff'; this.style.color='#ffffff';"
    onmouseout="this.style.backgroundColor='#f0f8ff'; this.style.color='#975ddaff';">
    Link To Demo File
  </a>
</div>
3. Open the file in Arduino IDE
4. Debug and Fix the errors in the demo file ***(Hint: Refer to the pinout diagram of our arduino.)***
5. Demo thermistor circuit working as intended:
    - Red LED should turn on when holding thermistor 
    - Yellow LED should turn on at room temperature 
    - Green LED should turn on when cold