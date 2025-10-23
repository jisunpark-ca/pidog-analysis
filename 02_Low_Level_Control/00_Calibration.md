# 📐 PIDOG Calibration Analysis: Hardware-Software Alignment

This document details the critical process of calibrating the PIDOG robot, focusing on the underlying hardware interaction and necessary logical justification for each step.

---

## 1. Calibration Objective (Logical Justification)

**Calibration** is the process of establishing the correct **neutral zero point** for each servo motor. This is necessary to compensate for two main factors:
1.  **Manufacturing Tolerance:** Inherent physical variances in the servo motors themselves.
2.  **Assembly Error:** Minor inaccuracies when assembling the robot's structure.

**Goal:** To ensure that when the software commands a servo angle of 90 degrees (often the neutral position), the physical servo horn is perfectly aligned according to the mechanical design.

---

## 2. Execution Procedure and Analysis

| Action Item | Command & Execution Environment | Hardware/Software Interaction |
| :--- | :--- | :--- |
| **Navigate** | `cd ~/pidog/examples` (RPi via SSH) | Locating the specific software module responsible for the zero-point routine. |
| **Execute** | `sudo python3 0_calibration.py` (RPi via SSH) | Runs the script with **root privileges (`sudo`)** to gain **direct hardware access** to the I2C bus or GPIO pins controlling the servos. |

### Key Concept: Why `sudo` is Non-Negotiable
The script needs to interact with the Raspberry Pi's **General Purpose Input/Output (GPIO)** pins or the **I2C bus** to send **Pulse Width Modulation (PWM)** signals to the servo driver board. In Linux, controlling these low-level hardware resources is restricted to the superuser (`root`) to maintain system security and stability.

---

## 3. Post-Calibration Verification (The Feedback Loop)

Software execution is only the first step. The critical part is verifying the physical result.

### Physical Verification Steps:
1.  **Visual Check:** After the script runs, physically inspect all **12 servo horns**. They should be in the straight, defined neutral position (often perpendicular to the servo body).
2.  **Adjustment Strategy:** If a servo is visibly misaligned:
    * **Priority 1 (Software Offset):** If the PIDOG library allows, adjust the servo offset value in the configuration file to compensate. This is the **software fix**.
    * **Priority 2 (Physical Reassembly):** If a software fix is unavailable or insufficient, the servo horn must be carefully removed and repositioned manually while the script is running.

### Abstraction: The PIDOG Control Cycle
Calibration ensures the **'Actuator Output'** stage of the PIDOG control cycle is accurate:

$$\text{Command Angle} \rightarrow \text{Control Signal (PWM)} \rightarrow \text{Physical Angle (Accurate)}$$
The calibration process validates the final step, ensuring the desired angle matches the actual physical position.

---