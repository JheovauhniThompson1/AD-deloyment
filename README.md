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

<img src="https://github.com/user-attachments/assets/c252bbb7-9ff7-4a3a-80f5-d84a4a615191"/>

</p>
<p>
Prior to building either of the Virtual Machines, I constructed a Virtual Network called "Active-Directory_VNet". This saves me the headache of having the Virtual Machine allocated to a randomly formed Virtual Network. It also assures that both of the Virtual Machines I'll be creating can share the same Virtual Network. After completing that, I went ahead and created both Virtual Machines: a Windows Server 2022 Virtual Machine.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/76a9664d-1c40-4df3-9515-b35d6879f35f"/>
</p>
<p>
In this step, I retrieved the Windows Server's private IP address, then went to the Windows 10 VM's network settings -> DNS settings and entered the Windows Server's IP address as the custom DNS. Before that though I did log into the Windows Server VM and disabled its firewall as well as making its NIC private IP Address static instead of dynamic.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/1c1d3c0a-ae89-4053-9f8b-edff70d1f72a"/>

</p>
<p>
For this final step, I performed a quick check to ensure both Virtual Machines were connected properly. While logged into the Windows 10 Virtual Machine, I opened PowerShell and ran the "ping" command with the Windows Server's private IP address, and the ping was successful!

Next, I ran "ipconfig /all" on the Windows 10 VM and confirmed that the Windows Server's private IP address appeared in the DNS settings section.
</p>
<br />
