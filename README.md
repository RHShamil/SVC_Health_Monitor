# Web Service Liveness Check Script

This project provides a bash script to check the liveness of a web service. It utilizes a cron job for scheduled execution, systemd for service management, and separate log files for success and failure events.

## Table of Contents

- [Introduction](#introduction)
- [Components](#components)
    - [Bash Script](#bash-script)
    - [Cron Job](#cron-job)
    - [Systemd Service](#systemd-service)
    - [Log Files](#log-files)
- [How it Works](#how-it-works)
- [Usage](#usage)
- [Benefits](#benefits)
- [Further Exploration](#further-exploration)

## Introduction

This project demonstrates how to create a robust web service liveness check script using bash. The script checks if the web service is running and accessible. It is scheduled to run periodically using cron, managed by systemd to ensure it starts on boot, and logs success and failure events to separate files for easy monitoring.

## Components

### Bash Script

The core of the project is the bash script. This script performs the following actions:

1. **Check Web Service:** It attempts to connect to the web service using a tool like `curl` or `wget`.
2. **Determine Status:** It checks the response code or output of the connection attempt to determine if the web service is running.
3. **Log Event:** Based on the status, it logs a success or failure message to the appropriate log file.

### Cron Job

Cron is a system utility that allows you to schedule commands or scripts to run at specific intervals. We'll use cron to run the liveness check script every 10 seconds.

### Systemd Service

Systemd is a system and service manager for Linux. We'll create a systemd service file to manage the web service, ensuring it starts automatically on boot and restarts if it crashes.

### Log Files

Two separate log files are used:

* **Success Log:** Records successful checks of the web service.
* **Failure Log:** Records failed checks, including any error messages.

## How it Works

1. **Systemd starts the web service on boot.**
2. **Cron runs the liveness check script every 10 seconds.**
3. **The script checks the web service's status.**
4. **The script logs the result (success or failure) to the appropriate log file.**
5. **Administrators can monitor the log files to track the web service's availability.**

## Usage

(Include example commands and explanations of how to use the script, configure the cron job, and set up the systemd service.  Also explain where the log files are located.)

## Benefits

* **Automated Monitoring:** The script automatically checks the web service's status, eliminating the need for manual checks.
* **Early Detection:** Frequent checks (every 10 seconds) allow for early detection of web service outages.
* **Logging:** Separate log files for success and failure events make it easy to diagnose issues and track availability.
* **Reliability:** Systemd ensures the web service starts on boot and restarts if it crashes.
* **Flexibility:** The script can be easily customized to check different aspects of the web service (e.g., specific URLs, response times).

## Further Exploration

* **Bash Scripting Tutorial:** Learn more about bash scripting and how to write effective scripts.
* **Cron Documentation:** Explore the full capabilities of cron for scheduling tasks.
* **Systemd Documentation:** Understand how systemd manages services and system startup.
* **Web Service Monitoring Tools:** Investigate dedicated web service monitoring tools for more advanced features and alerts.

This README provides a high-level overview of the project. The actual script, configuration files, and systemd service definition will be available in the repository files.
