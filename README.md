# 🧰 Bash Scripting Suite for System Maintenance

A comprehensive suite of **Bash scripts** designed to automate common system maintenance tasks — including backup, system updates, and log monitoring — through an interactive menu-driven interface.

---

## 📋 Table of Contents

- [Objective](#objective)
- [Features](#features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Script Details](#script-details)
- [Configuration](#configuration)
- [Logging](#logging)
- [Requirements](#requirements)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

---

## 🎯 Objective

This project aims to **streamline system administration** by automating routine maintenance tasks such as:

- System backups  
- System updates and cleanup  
- Log file monitoring  

---

## ✨ Features

- **Interactive Menu Interface** – User-friendly command-line menu for easy navigation  
- **Centralized Logging** – All operations are logged to `maintenance_suite.log` with timestamps  
- **Modular Design** – Separate scripts for each maintenance task  
- **Real-time Output** – Uses `tee` to display output while logging simultaneously  
- **Error Handling** – Proper input validation and error messages  

---

## 📁 Project Structure

├── `main_1.sh`              # Main menu script (entry point)<br />
├── `backup_1.sh`            # Backup script<br />
├── `maintenance.sh`         # System update and cleanup script<br />
├── `log_monitor_1.sh`       # Log monitoring script<br />
└── `maintenance_suite.log`  # Central log file (auto-generated)<br />

---

## ⚙ Prerequisites

- Linux/Unix operating system  
- Bash shell (version 4.0 or higher)  
- `sudo` privileges for maintenance and log monitoring operations  
- Required utilities: `tar`, `tee`, and either `apt` or `yum` (depending on your distribution)  

---

## 🧩 Installation

1. **Clone this repository:**

```bash
   git clone https://github.com/yourusername/bash-maintenance-suite.git
   cd bash-maintenance-suite
```

2. **Make all scripts executable:**

```bash
   chmod +x main_1.sh backup_1.sh maintenance.sh log_monitor_1.sh
```

3. **(Optional)** Ensure all scripts are in the same directory, or update the paths in `main_1.sh` accordingly.

---

## 🚀 Usage

Run the main script to access the interactive menu:

```bash
./main_1.sh
```

### Menu Options

| Option | Description                                                                                |
| ------ | ------------------------------------------------------------------------------------------ |
| 1      | **Run System Backup** – Creates compressed backups of specified directories                |
| 2      | **Run System Maintenance** – Performs system updates and cleanup *(requires sudo)*         |
| 3      | **Monitor System Logs** – Scans `/var/log/auth.log` for “Failed” entries *(requires sudo)* |
| 4      | **Exit** – Closes the suite                                                                |

All operations are **automatically logged** to `maintenance_suite.log` with timestamps for audit purposes.

---

## 🧠 Script Details

### `main_1.sh`

* Entry point providing an **interactive menu interface**.
* Coordinates the execution of other scripts.
* Manages **centralized logging** with `tee` for real-time display and persistent logging.

### `backup_1.sh`

* Handles **automated backup operations**.
* Creates **timestamped compressed archives** of important directories.

### `maintenance.sh`

* Performs **system maintenance tasks** including:

  * Package updates
  * System upgrades
  * Cache cleanup
  * Removal of unnecessary packages

### `log_monitor_1.sh`

* Monitors system logs (`/var/log/auth.log`) for **failed authentication attempts** or other specified patterns.

---

## ⚙ Configuration

Edit the configuration section in `main_1.sh` to customize paths and settings:

```bash
BACKUP_SCRIPT="./backup_1.sh"
MAINTENANCE_SCRIPT="./maintenance.sh"
LOG_MONITOR_SCRIPT="./log_monitor_1.sh"
LOG_FILE="maintenance_suite.log"
```

---

## 🪵 Logging

All script executions are logged to `maintenance_suite.log` with:

* Timestamps for each operation
* Complete output (`stdout` and `stderr`)
* Operation identifiers

View logs using:

```bash
cat maintenance_suite.log
```

Or monitor logs in real-time:

```bash
tail -f maintenance_suite.log
```

---

## 🧾 Requirements

* **Disk Space:** Adequate space for backups and logs
* **Permissions:** Sudo access for system maintenance and log monitoring
* **Network:** Internet connection required for system updates

---
