<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Depolying Active Directory within Azure Windows Server VM</h1>
This tutorial outlines the Setup and Installation of Active directory using a Windows Server Virtual Machine(Azure).<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- Active Directory Users and Computers

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment Steps</h2>

- Installed Active Directory Domain Services on Windows Server VM
- Created a new forest(can be named virtually anyting, just remember it)
- Created a Domain Admin in Active Directory users and Computers, as well as a Employees Organizational Unit(Future Reference)
- Created another OU(Organizational Unit) for the Windows 10 VM

<h2>Deployment Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/4740f8d5-1708-4b31-a84c-309139b7b219"/>

</p>
<p>
In the first step, I logged into the Windows Server VM, opened Server Manager, clicked on Add Roles and Features, and selected Active Directory Domain Services as the feature I wanted to add. The installation of this feature was then completed on the Windows Server VM. After the installation, I noticed the warning errors that appeared, and then I created a forest called "solaris.com" for Active Directory.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/c95b8609-d44f-40c6-b107-b8e1d2bafc3c"/>
<img src="https://github.com/user-attachments/assets/6a7db11a-a9c9-4eb4-9d02-b81f508c2e79"/>
</p>
<p>
For this step, I logged back into the Windows Server VM, which had been turned into a Domain Controller (referred to as the Domain Controller from now on) after it restarted. The first noticeable change was that I now had to log in using solaris.com\labuser. I then created a Domain Admin in Active Directory Users and Computers called "Jane Doe" (solaris.com\jane_admin, password: Password1), along with two Organizational Units: _EMPLOYEES and _ADMINS
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/d4554470-1d89-490a-92b1-beeb1ddee60c"/>
<img src="https://github.com/user-attachments/assets/9ee47b7d-9160-4445-81d0-24640d4980d7"/>
</p>
<p>
For this final step, I performed a quick check to ensure both Virtual Machines were connected properly. While logged into the Windows 10 Virtual Machine, I opened PowerShell and ran the "ping" command with the Windows Server's private IP address, and the ping was successful!

Next, I ran "ipconfig /all" on the Windows 10 VM and confirmed that the Windows Server's private IP address appeared in the DNS settings section.
</p>
<br />
