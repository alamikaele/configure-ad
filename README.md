<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create Resources To Start
- Creating Client-1 in Microsoft Azure
- Test Connectivity of Client to DC-1
- Install Active Directory
- Create Domain Admin User and Other Users in Domain
- Setup RDP for Non-Admin users on Client 1

<h2>Deployment and Configuration Steps</h2>

<h3 align="center"> Create Resources To Start </h3>

<p align="center">
Create Resource Group on Microsoft Azure
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Create Virtual Network on Microsoft Azure
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
<h4 align="center">Creating Domain Controller Virtual Machine (VM) </h4>
Create Virtual Machine on Microsoft Azure and name it "dc-1". Make sure to put it in the resource group and virtual network we just created. Image: Windows Server 2022. Size: anything with 2 virtual cpus. username: make it and save it in a txt file (notepad/textedit). password: no password
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>

<p align="center">
Log into VM and disable Windows Firewall. This tests connectivity
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Set Domain Controller's NIC Private IP address to be static
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>


<h3 align="center">Creating Client-1 in Microsoft Azure </h3>
<p align="center">
Create second virtual machine. Subscription: Pay-as-you-go. Same resource group as the first virtual machine. Name: "client-1". Image: Windows 10 Pro, version 22H2. Size: anything at least 2 vcpus. Username and passwords: username same as first vm but add password and save to txt file. Go to networking tab  
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Go to networking tab. Virtual network: same as one we created and put first vm in. Review + create
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Set Client-1 DNS settings to DC-1's private IP address
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Restart Client-1 from Azure portal
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center">Test Connectivity of Client to DC-1</h3>

<p align="center">
Ping DC-1's private IP address after logging in to Client-1
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Open PowerShell and run "ipconfig /all". Look for DNS Settings and it should have DC-1's Private IP address
</p>
<br/>
<p>
<img src="https://i.imgur.com/4tSKQkj.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>



