# splunk-bruteforce-detection-lab

# Splunk Brute Force Detection Lab

## Objective
Simulate a brute force attack on a Windows machine and detect it using Splunk SIEM and PowerShell automation.

## Tools Used
- Windows 10 VM
- Splunk Enterprise
- PowerShell
- VirtualBox

## Attack Simulation
Used PowerShell to generate failed login attempts (Event ID 4625).

## Detection Logic
SPL Query:
(index=wineventlog EventCode=4625 | bucket _time span=5m | stats count by _time, Account_Name | where count > 10)

## Dashboard
Includes:
- Failed login trends
- Targeted accounts
- Logon type distribution

## Automation
PowerShell script queries Splunk REST API for brute force detection.

## Skills Demonstrated
- SIEM log ingestion
- SPL query writing
- Windows event analysis
- PowerShell scripting
- SOC detection engineering
