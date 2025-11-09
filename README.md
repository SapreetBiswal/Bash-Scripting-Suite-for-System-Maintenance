Here's your professional README.md file without the embedded code:

markdown
# Bash Scripting Suite for System Maintenance

A comprehensive suite of Bash scripts designed to automate common system maintenance tasks including backup, system updates, and log monitoring through an interactive menu-driven interface.

## Table of Contents

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

## Objective

This project aims to streamline system administration by providing an automated solution for routine maintenance tasks such as:
- System backups
- System updates and cleanup
- Log file monitoring

## Features

- **Interactive Menu Interface**: User-friendly command-line menu for easy navigation
- **Centralized Logging**: All operations are logged to `maintenance_suite.log` with timestamps
- **Modular Design**: Separate scripts for each maintenance task
- **Real-time Output**: Uses `tee` to display output while logging simultaneously
- **Error Handling**: Proper input validation and error messages

## Project Structure


.
├── main_1.sh              # Main menu script (entry point)
├── backup_1.sh            # Backup script
├── maintenance.sh         # System update and cleanup script
├── log_monitor_1.sh       # Log monitoring script
└── maintenance_suite.log  # Central log file (auto-generated)


## Prerequisites

- Linux/Unix operating system
- Bash shell (version 4.0 or higher)
- `sudo` privileges for maintenance and log monitoring operations
- Required utilities: `tar`, `tee`, `apt` or `yum` (depending on your distribution)

## Installation

1. Clone this repository:

git clone https://github.com/yourusername/bash-maintenance-suite.git
cd bash-maintenance-suite


2. Make all scripts executable:

chmod +x main_1.sh backup_1.sh maintenance.sh log_monitor_1.sh


3. Ensure all scripts are in the same directory, or update the paths in `main_1.sh` accordingly.

## Usage

Run the main script to access the menu:


./main_1.sh


### Menu Options

1. **Run System Backup**: Creates compressed backups of specified directories
2. **Run System Maintenance**: Performs system updates and cleanup (requires sudo)
3. **Monitor System Logs**: Scans `/var/log/auth.log` for "Failed" entries (requires sudo)
4. **Exit**: Closes the suite

All operations are automatically logged to `maintenance_suite.log` with timestamps for audit purposes.

## Script Details

### main_1.sh
The main entry point that provides an interactive menu interface. It coordinates the execution of other scripts and manages centralized logging using the `tee` command to display output in real-time while saving to the log file.

### backup_1.sh
Handles automated backup operations. Creates timestamped compressed archives of important directories.

### maintenance.sh
Performs system maintenance tasks including:
- Package updates
- System upgrades
- Cache cleanup
- Removal of unnecessary packages

### log_monitor_1.sh
Monitors system logs (specifically `/var/log/auth.log`) for failed authentication attempts or other specified patterns.

## Configuration

Edit the configuration section in `main_1.sh` to customize script paths:


BACKUP_SCRIPT="./backup_1.sh"
MAINTENANCE_SCRIPT="./maintenance.sh"
LOG_MONITOR_SCRIPT="./log_monitor_1.sh"
LOG_FILE="maintenance_suite.log"


## Logging

All script executions are logged to `maintenance_suite.log` with:
- Timestamps for each operation
- Complete output (stdout and stderr)
- Operation identifiers

View logs using:

cat maintenance_suite.log
# or
tail -f maintenance_suite.log  # for real-time monitoring


## Requirements

- **Disk Space**: Adequate space for backups and logs
- **Permissions**: Sudo access for system maintenance and log monitoring
- **Network**: Internet connection required for system updates

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

This project was developed as part of a Capstone Project for learning system administration and Bash scripting automation techniques.

---

For questions or suggestions, please open an issue on GitHub.
