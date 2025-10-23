# Raspberry Pi Environment Setup Guide

This guide documents the necessary steps to remotely access the Raspberry Pi (RPi) and prepare the environment for cloning the PIDOG project.

## 1. Network & SSH Access Mastery

### Prerequisites
* **OS Installation:** OS successfully installed onto the Micro SD Card using **Raspberry Pi Imager**.
* **Network Connection:** RPi and the host PC must be connected to the **same local network**.
* **SSH Enabled:** SSH service must be enabled on the RPi configuration (either during Imager setup or via `sudo raspi-config`).

### Configuration: Necessary Interfacing Options

Before proceeding, critical hardware interfaces required for the PIDOG servos and sensors must be enabled via the configuration tool.

1.  **Launch Configuration Tool:**
    ```bash
    sudo raspi-config
    ```
2.  **Enable Interfaces (Interfacing Options):**
    * **P3 - I2C:** **Enable.** (Required for I/O expansion, often used by the servo driver board).
    * **P4 - SPI:** **Enable.** (Used for some peripheral communications, good practice to enable).
    * **P5 - VNC:** **Optional.** (Enable only if **Remote Desktop Access (GUI)** is required, but SSH is sufficient for coding).

### Procedure: SSH Connection

1.  **Establish SSH Connection:** Use the standard SSH command to connect remotely.
    ```bash
    ssh jisunpark@raspberrypi.local 
    ```
    * **Secure shell (SSH)** is a program that provides encrypted connections to a remote computer system.

---

## 2. PIDOG Project Preparation

Once SSH access is secured, the final step is to clone the project repository onto the RPi.

### Action A: Cloning the Forked Repository (The Origin)

1.  **Navigate to Project Directory:** Move to where you want to store the code (the home directory).
    ```bash
    cd ~ 
    ```
2.  **Clone my repository (the Origin):** Use the full Git command to pull the code from *my* GitHub fork.
    ```bash
    git clone git@github.com:jisunpark-ca/pidog-project-portfolio.git
    ```
3.  **Verify the Remote Connection:** Change into the newly cloned directory and confirm the `origin` remote is correctly set to your GitHub account.
    ```bash
    cd pidog-project-portfolio
    git remote -v
    ```
    * **Expected Output:** The output should clearly show your GitHub URL (`jisunpark-ca/pidog-project-portfolio.git`) for both `fetch` and `push` operations.

### Action B: Code Synchronization (Execution Readiness)

1. Local PC Synchronization (Origin Management)

    These commands are run on your **Local PC** to manage the connection to your GitHub repository (**Origin**) and verify your working status before pushing changes.

    | Command | Logical Purpose | Execution Location |
    | :--- | :--- | :--- |
    | `git remote -v` | **Verify Remote Connection.** Confirms that **`origin`** correctly points to **your private GitHub repository**. Crucial for checking if any `upstream` connection was unintentionally retained. | Local PC (PIDOG folder) |
    | `git branch -a` | **View All Branches.** Ensures you are operating on the correct branch (e.g., **`master`** / **`main`**) before making changes. | Local PC (PIDOG folder) |
    | **`git add .`** | **1. Stage Changes.** Moves all modified and new files to the staging area, preparing them for the final commit. | Local PC (PIDOG folder) |
    | `git commit -m "Feat: Implemented new walking gait"` | **2. Commit Changes.** Finalizes your code modifications and records them permanently in the local repository history. | Local PC (PIDOG folder) |
    | `git push origin master` | **3. Push to GitHub (Origin).** Uploads your committed changes to your centralized GitHub repository. **(Establishes Single Source of Truth)** | Local PC (PIDOG folder) |


2. RPi Synchronization (Fetching Latest Code)

    The RPi acts as the **execution environment** (the place where the hardware runs). It must pull the latest code from your central authority (GitHub) before running the program.

    | Command | Logical Purpose | Execution Location |
    | :--- | :--- | :--- |
    | `git pull origin master` | **Update Code.** Pulls the latest commits from your GitHub repository (**`origin`**)'s     **`master`** branch and merges them into the RPi's local repository. This ensures the RPi always runs the most current,     committed version of your code. | RPi (PIDOG folder, via SSH) |
---