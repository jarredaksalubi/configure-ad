# configure-ad# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Resources in Azure and Ensure Connectivity between client and Domain Controller
- Install Active Directory 
- Create an Admin and Normal User Account in AD
- Join Client-1 to your domain 
- Setup Remote Desktop for non-admin users and create additional users to attempt login into client-1

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/qrNnQex.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the Domain Controller VM in Microsoft Azure and set its NIC Private IP address to static. Create a Client VM using the same Resource Group and Vnet.-> Install the Active Directory Domain Services (AD DS) role: This is done through the Server Manager tool on your Windows Server. Simply select the AD DS role and follow the prompts to install it.
</p>
<br />

<p>
<img src="https://i.imgur.com/vUgJPdp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure the domain name: During the AD DS installation, you'll be prompted to specify a domain name. This will be the name of your Active Directory domain, and it should be unique and not already in use. Ensure connectivity between the client and Domain Controller by pinging DC-1's private IP address with ping -t <ip address> and enabling ICMPv4 in the local windows Firewall of the Domain Controller.
</p>
<br />

<p>
<img src="https://i.imgur.com/2u3ayVZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Join computers (client-1) to the domain: Once Active Directory is set up, you can join your computers to the domain. This is done through the system properties settings on each computer.
</p>
<br />
<img src="https://i.imgur.com/RxrMKPr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Setup Remote Desktop for non-administrative users on Client-1 and create additional users by running a PowerShell script on DC-1.->> Create user accounts and assign permissions: With Active Directory set up and your computers joined to the domain, you can start creating user accounts and assigning permissions to them. This allows you to control access to network resources and ensure that only authorized users can access sensitive information.
