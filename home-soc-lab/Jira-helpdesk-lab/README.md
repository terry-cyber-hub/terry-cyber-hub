**IT Help Desk Lab — Jira Service Management Simulation**






**Project Overview**

This project is a simulated IT help desk environment where I practiced real-world IT support tasks using a ticketing system. I used this lab to learn how IT technicians handle common user problems, document issues, and resolve tickets like in a real company.




**I simulated two main support tickets:**

- Account lockout
- Password reset


**Tools Used**
Jira Service Management — for creating and managing IT support tickets

VMware Workstation — for running virtual machines

Windows Server 2022 — used as the domain controller in the lab

Windows 11 — used as the client machine

**Lab Setup**



**I built a small virtual IT environment:**

- Windows Server 2022 acting as a Domain Controller
- Windows 11 client machine joined to the domain
- Both machines running inside VMware Workstation Pro
- Jira Service Management used as the help desk system
- Tickets I Simulated and Resolved



**1. Account Lockout**


Problem:
The user account was locked after multiple failed login attempts.

What I did:

- Checked Active Directory for locked account
- Unlocked the user account
- Reset password when needed
- Tested login on Windows 11 client

Result:


User was able to log in successfully again.

**2. Password Reset**


Problem:
User forgot their password and could not log in.



**What I did:**

Located user in Active Directory
Reset password
Forced password change at next login
Verified login from Windows 11 client

**Result:**
User successfully logged in with new password.

**Skills Practiced**


- IT troubleshooting and problem solving
- Active Directory user management
- DHCP and network troubleshooting
- Password and account management
- Ticket documentation in Jira
- Simulating real IT support workflows



**What I Learned**

This project helped me understand how real IT help desk environments work. I learned how to:

- Diagnose common user issues
- Work through structured troubleshooting steps
- Document solutions clearly in a ticketing system
- Use Windows Server tools in a practical way

**Screenshots:**
<img width="1877" height="935" alt="Screenshot 2026-05-25 214003" src="https://github.com/user-attachments/assets/be28f78b-05d3-4b47-9fa9-387a57637cc6" />
* Figure 1: The client's password was successfully changed
<img width="515" height="386" alt="Screenshot 2026-05-25 214245" src="https://github.com/user-attachments/assets/e83fda39-5a15-4867-b8e1-0e093f2af424" />

* Figure 2: The client's account was unlocked due the lockout from login attempts
<img width="1919" height="1079" alt="Screenshot 2026-05-25 213757" src="https://github.com/user-attachments/assets/528ba4a1-f6c1-4ea6-9669-ff6e6b58cd2d" />
* Figure 3: This is the virtual environment (VMware workstation Pro) where the project was executed




**Screenshots of The Tickets**
<img width="1896" height="1008" alt="Screenshot 2026-05-25 205116" src="https://github.com/user-attachments/assets/54283d2a-bfda-4666-b02a-f7584c031c46" />
* Figure 1: This image shows all the issue types in the IT Helpdesk Lab
<img width="1918" height="904" alt="Screenshot 2026-05-25 212627" src="https://github.com/user-attachments/assets/c1bc0176-e303-4962-a763-a325886b49f2" />
<img width="1358" height="906" alt="Screenshot 2026-05-25 205548" src="https://github.com/user-attachments/assets/8ebf35ea-80ef-4dbe-a9d8-0155d934da70" />



