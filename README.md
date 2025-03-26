# **RSSI-Based Indoor Localization using ESP32**  


## **Project Overview**  
Indoor localization has remained a significant challenge for decades, with applications spanning various industries, including smart buildings, healthcare, and robotics. In this project, we will develop an **end-to-end localization system** based on **Wi-Fi Received Signal Strength Indicator (RSSI)**.  

The project consists of the following key components:  
1. **RSSI Data Collection**: Capturing RSSI values from an ESP32 IoT device.  
2. **Data Transportation**: Transmitting RSSI data to an edge/cloud server for processing.  
3. **Localization Algorithm**: Implementing an algorithm to estimate the client’s location based on RSSI data.  
4. **System Evaluation**: Analyzing system performance using benchmark datasets and real-world tests.  

Each team will be provided with an **ESP32 module** and a **pre-processed RSSI dataset** based on public sources.  

## **Learning Outcomes**  
By completing this project, we aim to gain proficiency in:  
✅ Configuring and using an IoT device (ESP32) to fetch RSSI data.  
✅ Performing Wi-Fi scanning and RSSI measurements.  
✅ Implementing MQTT for IoT data transportation.  
✅ Designing and developing RSSI-based localization algorithms.  
✅ Evaluating system performance and analyzing results.  
✅ Building an end-to-end system through effective team collaboration.  

---

## **Project Tasks and Implementation**  

### **Task 1: Obtaining RSSI Data using ESP32**  
Instead of using laptops or smartphones as clients, we will utilize an **ESP32 module** to measure RSSI values from surrounding Wi-Fi Access Points (APs).  

🔹 **Implementation Steps:**  
- Familiarize with ESP32 device specifications.  
- Develop firmware to scan for surrounding APs.  
- Collect RSSI values with corresponding **MAC addresses** of detected APs.  
- Implement configurable **scanning intervals** for optimized performance.  

📝 **Expected Output:** A list of **RSSI values** and associated **AP MAC addresses**, captured periodically.  

---

### **Task 2: Wi-Fi Connection and Data Transportation**  
To enable communication between the ESP32 and the host machine, we will establish a **wireless connection** using one of the following methods:  
1. Connecting both ESP32 and the host machine to the **same network** (e.g., HKU Wi-Fi or a home router).  
2. Creating a **Wi-Fi hotspot** on the laptop and connecting the ESP32 to it.  

#### **Data Transmission via MQTT**  
We will implement **MQTT (Message Queuing Telemetry Transport)** for efficient data exchange between devices.  

🔹 **System Architecture:**  
- **ESP32 (Client)**:  
  - **Publisher**: Sends RSSI data.  
  - **Subscriber**: Receives commands from the UI.  
- **Host Machine (Broker)**:  
  - Forwards messages between publishers and subscribers.  
- **Processing Engine** (runs on the host machine):  
  - **Subscriber**: Receives and processes RSSI data.  
  - **Publisher**: Sends control commands (e.g., start/stop data collection).  

📝 **Expected Output:** ESP32 successfully transmits RSSI data to the broker, which is forwarded to the engine for further processing.  

---

### **Task 3: Localization Algorithm Implementation**  
We will design and implement an **RSSI-based localization algorithm** using known **AP locations** and measured RSSI values.  

#### **Potential Approaches:**  
1. **Maximum RSSI-based Localization**  
   - Assigns the client’s location to the **AP with the highest RSSI**.  
   - **Pros:** Simple but inaccurate.  
2. **Weighted Centroid Localization**  
   - Uses **RSSI values as weights** to estimate the client’s position.  
   - Example weighting method: \( w_i = \frac{1}{RSSI_i} \).  
3. **Ranging-based Localization (Trilateration)**  
   - Converts RSSI to distance using **path loss models**.  
   - Uses the **Least Squares Method** for accurate localization.  
   - Empirical tuning of path loss parameters may improve accuracy.  

📝 **Expected Output:** A functional localization algorithm that estimates the client’s position based on input RSSI values and AP locations.  

---

### **Task 4: System Evaluation**  
To assess the performance of our localization system, we will use a **pre-processed dataset** that includes:  
- **RSSI Matrix**: \([n_{\text{datapoints}} \times n_{\text{AP}}]\)  
- **Ground Truth Labels**: \([n_{\text{datapoints}} \times 2]\)  
- **AP Locations**: \([n_{\text{AP}} \times 2]\)  

#### **Evaluation Metrics:**  
- Compute **Euclidean distance errors** between predicted and actual locations.  
- Plot results using a **Cumulative Distribution Function (CDF)** for error distribution.  

📝 **Expected Output:** A detailed **performance analysis**, including accuracy metrics and graphical visualizations.  

---

## **Technology Stack & Tools**  
✅ **Hardware**: ESP32 module  
✅ **Programming Languages**: Python, C++ (for ESP32 firmware)  
✅ **Communication Protocol**: MQTT  
✅ **Wi-Fi Scanning**: ESP-IDF / Arduino ESP32 SDK  
✅ **Localization Algorithms**: NumPy, SciPy, OpenCV  
✅ **Evaluation & Visualization**: Matplotlib, Pandas  

---

## **Project Timeline**  
| Task | Milestone | Deadline |  
|------------|------------------------------------------------|-------------|  
| Task 1 | Collect and store RSSI data from ESP32 | Week 1-2 |  
| Task 2 | Establish Wi-Fi connection and MQTT messaging | Week 3-4 |  
| Task 3 | Implement and test localization algorithm | Week 5-6 |  
| Task 4 | Evaluate system performance and finalize results | Week 7-8 |  

---



---

## **Conclusion**  
This project aims to develop an **efficient and scalable** RSSI-based indoor localization system using ESP32, MQTT, and advanced localization algorithms. Through this project, we will gain hands-on experience in IoT communication, data processing, and algorithm development, which are crucial skills in modern **wireless networking and AI-driven localization systems**.  

🚀 **Final Deliverables:**  
✅ Fully implemented **localization system**  
✅ **Performance evaluation report**  
✅ **Codebase & Documentation**  

---
