---
title: AI/ML
parent: Onboarding
nav_order: 2
---

## AI / ML Onboarding

***

### **Role Purpose**
The AI/ML role focuses on transforming raw biomedical sensor data (from Arduino Nano 33 BLE Sense) into meaningful predictions, bridging data science and embedded systems. With this role, you will assist in enabling our projects to do things like detect heart rate, classify breathing patterns, or recognize voice commands. Through this onboarding and our projects you’ll learn how to:
- Collect and clean biosignal data.
- Extract features that highlight patterns in physiological signals.
- Train machine learning models (locally or with Edge Impulse).
- Deploy models efficiently onto microcontrollers for real-time inference.

***

### **Why This Role Matters**
- Raw data is meaningless until processed. AI/ML turns numbers into useful biomedical insights.
- Real-time embedded ML unlocks portable medical tools (e.g., low-power sleep apnea detectors, stethoscopes, arrhythmia detection).
- Your work ensures EMBS projects are smart, innovative, and impactful.

***

### **Onboarding Process**
1. **Learn** → Complete tutorials/resources.
2. **Learning Check** → Google form submission.
3. **Demo** → Successfully deploy and demonstrate EMG model.
4. **Review** → Officer approves learning check submission, demo, and demo file submission.
5. **Role Assignment** → Discord role updated to AI/ML
6. **Integration** → Begin contributing ML models to real club projects.

***

### **Skills to Learn**
**Data Pipelines**
- How to collect sensor data from Arduino BLE Sense.
- Cleaning noisy signals (filtering, normalization).
- Labeling datasets for supervised ML tasks.

**Feature Extraction**
- Time-domain: mean, variance, zero-crossings.
- Frequency-domain: Fourier Transform (FFT), spectrograms.

**ML Frameworks**
- Edge Impulse: beginner-friendly platform for embedded ML.
- TensorFlow Lite Micro: running models directly on MCUs.
- scikit-learn: simple Python models for rapid testing.

**Embedded Deployment**
- Quantization: shrinking models for MCU use.
- Model conversion: preparing .tflite files.
- Loading models: deploying to Arduino BLE Sense.

***

### **Learning Tools**
**Data Pipelines (collect, clean, label sensor data)**
- [**Signal Processing Techniques in Python (SciPy Docs)**](https://docs.scipy.org/doc/scipy/tutorial/signal.html)
    - Covers filtering, normalization, and basic preprocessing for noisy biosignals.


**Feature Extraction (turning raw data into inputs for ML)**
- [**Feature Extraction from Time Series – sktime Documentation**](https://www.sktime.net/en/v0.27.1/examples/transformation/feature_extraction_with_tsfresh.html)
    - Shows how to compute time-domain (mean, variance, zero crossings) and frequency-domain (FFT, spectrogram) features.
- [**Harvard: Fourier Transforms and Signal Processing Notes**](https://scholar.harvard.edu/files/schwartz/files/lecture8-fouriertransforms.pdf)
    - Clear written notes on FFTs, spectrograms, and their use in biosignal analysis.


**ML Frameworks (training + testing models)**
- [**Edge Impulse + Arduino Docs**](https://docs.arduino.cc/tutorials/nano-33-ble-sense-rev2/edge-impulse/)
    - Beginner-friendly: step-by-step for training and deploying models with Arduino Nano BLE Sense.
- [**scikit-learn User Guide**](https://scikit-learn.org/stable/user_guide.html?utm_source=chatgpt.com)
    - Teaches classical ML (SVM, Random Forest, logistic regression) for prototyping with labeled datasets.
- [**TensorFlow Lite Micro Documentation**](https://cms.tinyml.org/wp-content/uploads/2020/09/bay-area-situnayake.pdf)
    - Covers running ML on microcontrollers, including Arduino boards.


**Embedded Deployment (making ML models run on tiny devices)**
- [**TensorFlow Lite Model Optimization Toolkit**](https://www.tensorflow.org/model_optimization?utm_source=chatgpt.com)
    - Explains quantization and model shrinking for embedded deployment.
- [**TinyML Book (free online previewt)**](https://tinymlbook.com/?utm_source=chatgpt.com)
    - Great for understanding the whole pipeline: sensors → features → ML → deployment on MCUs.

***

### **Learning Check**
Complete this [**knowledge check**](https://docs.google.com/forms/d/1vInHmMKSFMmLrvQQvm2Bx9O_96A56G1jYdF1RmZ5AUw/edit) using the materials above.

***

### **Demo**
This part of the guide walks you through installing TensorFlow Lite Micro on Arduino, reading EMG data from a uMyo BLE sensor, training a simple ML model in Python, and running that model back on the Arduino.

**Create Your Working Folder**
- Download and extract the master [**embs_ml_training folder**](https://drive.google.com/drive/folders/1W38WlS7jkQersILVUn3qNbmc1ruTAO9t?usp=drive_link) and extract to location of your choosing
    - You’ll store all related files here: Arduino sketches, Python scripts, and EMG data.

**Install TensorFlow Lite for Arduino**
- Instructions: [**Official TFLite Micro Arduino Examples**](https://github.com/tensorflow/tflite-micro-arduino-examples#checking-your-installation)
    - ***(If you don’t have Git, install it from [**Git Download**](https://git-scm.com/downloads))***


<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
  <strong>Open your terminal (or Git Bash) and run:</strong>
  <ul>
    <li><em>cd ~/Documents/Arduino/libraries or whatever path to your arduino libraries</em></li>
    <li><em>git clone https://github.com/tensorflow/tflite-micro-arduino-examples.git</em></li>
  </ul>
</div>


<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
  <strong>Check or Create the Version Header:</strong>
  <ul>
    <li><em>Go to the folder:</em> <code>Documents/Arduino/libraries/Arduino_TensorFlowLite/src/tensorflow/lite/</code></li>
    <li><em>If you don’t see <code>version.h</code>, create it by copying and pasting the 
      <a href="https://drive.google.com/file/d/1plumm5Z7CE2TakniAVI2HegowyftfRPO/view?usp=drive_link"><strong>version.h file</strong></a> 
      or by copying one of the other <code>.h</code> files and renaming it to <code>version.h</code>. Within this file, paste:</em>
      <pre><code>
        #ifndef TENSORFLOW_LITE_VERSION_H_
        #define TENSORFLOW_LITE_VERSION_H_
        #define TFLITE_SCHEMA_VERSION (3)
        #endif  // TENSORFLOW_LITE_VERSION_H_
      </code></pre>
    </li>
  </ul>
</div>


<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
  <strong>Verify Installation:</strong>
  <ul>
    <li><em>Open Arduino IDE → File → Examples → Arduino_TensorFlowLite</em></li>
    <li><em>Try uploading an example (like hello_world).</em></li>
    <li><em>If it compiles and uploads successfully, TensorFlow Lite is installed!</em></li>
  </ul>
</div>


<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
    <text>
        Note: This section helps you install the embedded ML framework that allows microcontrollers to run neural networks offline.In EMBS, this is crucial for real-time analysis of biosignals like EMG or ECG directly on the device without needing a laptop — improving portability and patient accessibility.
    </text>
</div>


**Set Up Mircophone Sensor Sensor**
- Wire the microphone to the arduino
- Plug arduino and microphone into breadboard
- Wire the 3.3V pin on the arduino to the red breadboard railing
- Wire the ground pin on the arduino to the blue breadboard railing
- Wire the A0 pin on the arduino to the OUT pin on the microphone (MAX4466)
- Wire the VCC pin on the microphone to the red breadboard railing
- Wire the GND pin on the microphone to the blue breadboard railing
- Here is a completed wiring of the devices:
![Serial Monitor](/assets/images/ai_microphone.png)
- Upload save the mic input folder to your computer
- Open the mic_input.ino file
- Plug in the USB cord from your computer to the arduino if you havent already
- Upload the code to the arduino
- Open Serial Monitor
- Speak and hold the same volume into the microphone
    - You should see numbers changing.
![Serial Monitor](/assets/images/ai-serial_monitor.png)
 - Switch to **Serial Plotter** to visualize it.
    - Values rise when you flex and fall when relaxed.
    - If no change, ensure your device is paired and connected via BLE.
![Serial Plotter](/assets/images/serial_plotter.png)

<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
    <text>
        Note:This step introduces biosignal acquisition — how medical devices collect data from sensors. You learn how to interface sensors (like EMG or heart rate monitors) with microcontrollers, a key part of signal preprocessing and device calibration in biomedical systems.
    </text>
</div>

 
**Collect Microphone Data**
- Paste the code from the embs_data_collection.ino file in the embs_ml_training folder into the sketch and upload.
- Download [**CoolTerm**](https://coolterm.en.lo4d.com/windows) (free serial monitor):
![CoolTerm](/assets/images/coolterm.png)
- Close Arduino’s Serial Monitor (only one app can use the port).
- Open CoolTerm → Options → Serial Port → choose the same COM port you have been using
![Serial Port](/assets/images/coolterm-serial_port.png)
- Set the file capture to these settings
![File Capture](/assets/images/file_capture-settings.png)
- Click Connect,  you should see live readings.
![Connect](/assets/images/ai-connect.png)
- Press Ctrl + R to start recording data and Press Ctrl + R again to stop recording
- Flex and rest separately for 15–30 seconds each:
- Turn off uMyo in between recordings to save battery.
<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
  <strong>Save 2 files in your embs_ml_training folder:</strong>
  <ul>
    <li><em>emg_rest.txt</em></li>
    <li><em>emg_flex.txt</em></li>
  </ul>
</div>
- Open the text files and delete outliers from the start and end of your recordings

<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
    <text>
        Note: This teaches data collection and labeling, fundamental for any ML-based medical device. You’re building a dataset,  the same process used to train algorithms for diagnosing muscle disorders, hand tremors, or neural responses.
    </text>
</div>

**Train the Machine Learning Model**
- Install latest version of [**Python 3**](https://www.python.org/downloads/)

<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
  <strong>In terminal (inside your embs_ml_training folder), run:</strong>
  <ul>
    <li><em>pip install tensorflow pandas scikit-learn numpy matplotlib</em></li>
    <li><em>pip install seaborn jupyter</em></li>
  </ul>
</div>

- Open train_emg_model.py (from the provided [**files**](https://drive.google.com/drive/folders/1W38WlS7jkQersILVUn3qNbmc1ruTAO9t?usp=drive_link) or repo).
![Train EMG](/assets/images/ai-train-emg.png)

<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
  <strong>Run this file in the terminal with:</strong>
  <ul>
    <li><em>python train_emg_model.py</em></li>
  </ul>
</div>

<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
  <strong>The script will:</strong>
  <ul>
    <li><em>Read your data files.</em></li>
    <li><em>Train a basic neural network.</em></li>
    <li><em>Generate a model.h file for Arduino.</em></li>
    <li><em>Create scalar_constants.txt with normalization values.</em></li>
  </ul>
</div>

<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
    <text>
        Note This teaches you model training and feature normalization, skills used in AI-driven biomedical devices (e.g., detecting arrhythmia or muscle fatigue). By training your own model, you understand how signal features (mean, RMS) translate into predictive patterns that help diagnose conditions or detect movement.
    </text>
</div>

**Deploy Model to Arduino**
- Copy model.h → into your Arduino sketch folder.
- Open a new sketch and paste the code from emg_training.ino in the embs_ml_training folder given to you
<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
  <strong>Copy the scalar constants from scalar_constants.txt into your Arduino sketch:</strong>
  <ul>
    <li><em>float mean_mean = FILL HERE;</em></li>
    <li><em>float std_mean  = FILL HERE;</em></li>
    <li><em>float mean_rms  = FILL HERE;</em></li>
    <li><em>float std_rms   = FILL HERE;</em></li>
  </ul>
</div>
- Upload to Arduino.
<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
    <text>
        Note:This step teaches embedded inference deployment — how trained AI models are run locally on devices like wearables. This is vital for real-time, low-power medical systems, such as prosthetic muscle control or heart rhythm monitoring.
    </text>
</div>

**Test the Model**
- Open Serial Monitor and flex or rest.
- The output should indicate which state (rest, pinch, flex) is being recognized.
![Test Model](/assets/images/ai-test_model.png)
- Demonstrate your working model to the club chair.
- Submit all files used here.
<div style="border: 2px solid #ccc; padding: 12px; border-radius: 8px; background-color: #f9f9f9;">
    <text>
        Note: This stage demonstrates real-time device feedback, showing how sensors and ML models can work together.It’s the same process used in smart prosthetics, rehabilitation aids, and portable diagnostics, where user actions or biological changes trigger intelligent response
    </text>
</div>
