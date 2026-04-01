## Summary of Findings 
The logs indicate that there is a brute force attack to try to gain unauthorized access to the device. Specifically, 
the brute force attack at two different time frame, 3:35pm and 9:42pm. Four attempts were done on the first brute force attempt
and five attempts at the second. The attack was done by gaining unauthorized physical access to the device. Due to the fact that consecutive login attempts happened 
at two different time solidifies the speculation that this incident is a brute force attack. 

### Detection Logic and Evidences
- The device has been found on a freshly restarted state even though the user is currently using the device before going on a break. Windows explicitly asks the user if they want to reschedule a restart or restart it now for an update so the employee must have known they authorized a restart for an update.
- Upon further inspection of the incident, logs presented consecutive failed login attempt in a short interval that all have a source network address of 127.0.0.1 which is a loopback address.
- The consecutive failed attempts within a short time frame and different hours is another evidence that suggest a brute force attack.


![brute_force_evidence](https://github.com/user-attachments/assets/de3f53a8-6ec0-4ee6-9453-b04917b5e7dd)

<br>

### What should be done
#### Preventive Controls
- Limited number of attempts for login should be implimented to avoid brute force attacks
- Strong password policies must be used to reduce the chance of guessing the credentials for access
- Multi-Factor Authentication (MFA) can be layered for additional security feature which also minimizes brute force attacks

#### Detection Improvements
- SIEM can be integrated to the network to detect threats and vulnerabilities earlier to contain them and solve for them in a controlled environment

### Limitations
- No automated detection system (SIEM) was used in this scenario
- Type 3 logon or accessing the device over the network for more complexity was not used or mixed in this simulation
