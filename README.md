# PIDOG System: Python Programming & Control

This repository serves as a personal learning resource detailing the in-depth analysis and documentation of the PIDOG system from a programming and system control perspective. The goal is to simultaneously acquire Python-based low-level control techniques and an understanding of Operating System principles using the PIDOG system.

**Reference:** [SunFounder](https://docs.sunfounder.com/projects/pidog/en/latest/python/python_start/installing_the_os.html)

## Topics & Structure

| Folder/Document | Topic | Details (Learning Objectives) |
| :--- | :--- | :--- | :--- |
| `01_System_Setup/` | **OS & Initial Environment** | Install Raspberry Pi OS, verify **I2C & SPI interfaces**, install all Python modules, Servo calibration, and system initialization analysis. |
| `02_Low_Level_Control/` | **Basic Movement & Actuator Control** | PiDog initialization, control of **leg/head/tail movement**, stop all actions, execute preset actions (Python for low-level control). |
| `03_Sensor_Input/` | **Sensor Data Reading & Processing** | Read **Distance sensor** values, analyze **IMU data** (gyro/accel), detect sound direction, handle head pat events. |
| `04_Advanced_Behaviors/` | **Integrated Projects & Advanced Features** | Analyze complex sensing and control logic for **Patrol**, **Face Track**, **Ball Track**, and Balance. |
| `05_OS_Automation/` | **OS Automation & Interaction** | Configure **Autostart PiDog on Boot**, control via keyboard and app (Input/Output and OS background processes). |

## Technologies Used

A list of primary tools and technologies used for this learning and analysis project:

* **Language:** Python
* **Platform:** Raspberry Pi 5 OS
* **Documentation:** Markdown

## Getting Started

Follow these steps to utilize the code and learning materials in this repository

### Environment Setup

1.  Clone the repository:
    ```bash
    git clone https://github.com/jisunpark-ca/pidog-learning.git
    cd pidog-learning
    ```
2.  Refer to the documentation in the `01_System_Setup/` folder to configure necessary dependencies and the environment.

## Contribution

While this is a personal study repository, feedback on system analysis or suggested improvements are welcome.

* Report errors or suggestions via **Issues**.
* (Optional) Propose direct changes through **Pull Requests**.

## License

All learning materials and documentation in this repository follow a Creative Commons License.

* **License:** **CC BY-NC-SA 4.0** (Attribution-NonCommercial-ShareAlike)
* **Summary:** You must give credit to the creator, use the material for non-commercial purposes only, and share any adaptations under the same license.

## Contact

* **Author:** Jisun Park
* **GitHub:** @jisunpark-ca
* **Email:** jisunpark28@gmail.com

