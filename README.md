# PIDOG System: Python Programming & Low-Level Control

This repository serves as a personal learning resource detailing the in-depth analysis and documentation of the PIDOG system from a programming and system control perspective. The goal is to simultaneously acquire Python-based low-level control techniques and an understanding of Operating System principles using the PIDOG system.

## Topics & Structure

| Folder/Document | Topic | Details (Learning Objectives) | Source Reference |
| :--- | :--- | :--- | :--- |
| `01_System_Setup/` | **OS & Initial Environment** | Install Raspberry Pi OS, verify **I2C & SPI interfaces**, install all Python modules, Servo calibration, and system initialization analysis. | 1. Quick Guide on Python, 2. Calibrate the PiDog |
| `02_Low_Level_Control/` | **Basic Movement & Actuator Control** | PiDog initialization, control of **leg/head/tail movement**, stop all actions, execute preset actions (Python for low-level control). | 4. Easy Coding (Initialization, Leg/Head/Tail Move, etc.) |
| `03_Sensor_Input/` | **Sensor Data Reading & Processing** | Read **Distance sensor** values, analyze **IMU data** (gyro/accel), detect sound direction, handle head pat events. | 4. Easy Coding (Read Distance, IMU Read, Sound Direction Detect, etc.) |
| `04_Advanced_Behaviors/` | **Integrated Projects & Advanced Features** | Analyze complex sensing and control logic for **Patrol**, **Face Track**, **Ball Track**, and Balance. | 3. Fun Python Projects |
| `05_OS_Automation/` | **OS Automation & Interaction** | Configure **Autostart PiDog on Boot**, control via keyboard and app (Input/Output and OS background processes). | Play with PiDog with Keyboard/APP, Autostart PiDog on Boot |
