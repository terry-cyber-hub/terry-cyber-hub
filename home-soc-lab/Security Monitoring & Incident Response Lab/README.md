# Security Monitoring & Incident Response Lab

## Project Overview
This project involved configuring advanced Windows security auditing policies, simulating a brute-force attack resulting in an account lockout, and analyzing the resulting security telemetry within a VMware lab environment. The objective was to practice foundational incident response, log analysis, and structured troubleshooting methodologies.

### Skills Demonstrated
* **OS Telemetry & Logging:** Configuring Windows Local Security Policies for advanced auditing.
* **Attack Simulation:** Generating intentional authentication noise and service lockouts.
* **Log Analysis & Forensics:** Extracting critical indicators of compromise (IoCs) from Windows Event Viewer.
* **Troubleshooting Methodology:** Analyzing event sub-status codes to diagnose authentication failures.

---

## Phase 1: Baseline Configuration & Auditing
Advanced security auditing was enabled via the Local Security Policy (`secpol.msc`) to ensure Windows captured granular authentication failures:

1. Navigated to `Local Policies -> Audit Policy`.
2. Enabled **Success** and **Failure** auditing for **Audit logon events** and **Audit account management**.
3. Enforced the active policy via the command line: (gpupdate /force)

   Phase 2 & 3: Attack Simulation, Incident Investigation & Log Analysis
To simulate an adversary attempting a brute-force attack, a local user account (bwayne) was targeted. Multiple explicit interactive authentication failures were forced from the command line, and Windows Event Viewer (eventvwr.msc) was used to isolate and analyze the generated security telemetry.

1. Simulating the Attack & Triggering Lockout
The following command was executed with intentionally incorrect passwords to force authentication failures:

DOS
runas /user:bwayne notepad.exe
After the 3rd consecutive incorrect password attempt, the system actively blocked authentication and returned System Error 1909: The referenced account is currently locked out.

2. Analyzing Event ID 4625: An Account Failed to Log On
This event captured the initial brute-force phase. Key forensic details extracted from the log details include:

Target Account: bwayne

Logon Type: 2 (Interactive - indicating a direct local attempt via an interface)

Sub Status Code: 0xc000006a (User typed the wrong password)

(Note: Initial attempts prior to creating the user account returned sub-status 0xc0000064, indicating the username did not exist).

3. Analyzing Event ID 4740: A User Account Was Locked Out
This event marked the mitigation threshold. The log explicitly documented the exact timestamp the target account was locked and identified the originating computer name.

Key Takeaways & Incident Response Methodology
Distinguishing Intent: A single Event 4625 with sub-status 0xc000006a typically indicates a standard user typo. A rapid succession of multiple 4625 events followed immediately by a 4740 lockout signals an automated or systematic brute-force attempt.

Username Enumeration: Tracking sub-status 0xc0000064 allows analysts to identify when an adversary is actively guessing or scanning for valid usernames across a system or network domain.


**Screenshots**:



<img width="843" height="706" alt="Screenshot 2026-05-29 114845" src="https://github.com/user-attachments/assets/56d1bf03-722d-4217-bea0-d5e5216ca458" />

Figure 1: This image illustrates the 4740 log that represents "account lockout"




<img width="851" height="708" alt="Screenshot 2026-05-29 112744" src="https://github.com/user-attachments/assets/987ded2e-1610-4adb-b2f8-c9857de6d3f3" />


 
Figure 2: This screenshot is showing log 4625 in event viewer, which illustrates failed login attempts




<img width="422" height="321" alt="image" src="https://github.com/user-attachments/assets/74159d66-6b2b-4672-8bd1-0c5f90940b4e" />



Figure 3: This is me trying to forcer the targeted account to lock out by running "runas /user:bwayne notepad.exe" in the command line
