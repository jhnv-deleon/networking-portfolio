# Identifying Brute Force Attack Using Windows Event Viewer

## Objective
- This project demonstrates how to identify brute force attack attempt of a threat actor by utilizing Windows Security Event Logs.
- Understand the importance of knowing how to use log viewer to identify if there are compromise on security or present vulnerabilities on the system.

### Tools Used
- Windows Event Viewer
- PowerShell

### Attack Simulation
The attack was simulated by intentionally logging in wrong credentials at the login screen in quick sucession. This method simulates the scenerio in which threat actor gained unauthorized physical access to device and trying to gain access by guessing the password of the device. 

### Log Analysis Process 
1. Open Event Viewer
2. Navigate to Windows Logs tab and select the Security sub-category
3. Select Filter Current Log and select the duration and type in "4625" at the Event ID filter
4. Analyze and Identify repeated attempts from the same account within a short time period

### Detection Indicators
- Multiple failed login attempts within a small time frame
- The attempts are all logon type 2 which means that the login attempt happened in the physical environment.
- The device was observed on its "post restart" state after the employee came back after some time. This is a defense mechanism of Windows which requires restart if the user guessed the password many times.  
