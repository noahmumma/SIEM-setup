<p align="center">
<img src="https://i.imgur.com/Y6kPrX0.jpeg" alt="SIEM Logo"/>
</p>


<h1>Setup and Deployment of Security Information and Event Management (SIEM) and Extended Detection and Response (XDR) tools on Linux VM</h1>
This tutorial outlines the setup and deployment of Wazuh's combined SIEM and XDR tool on a Linux virtual machine.<br />

<h2>Environments and Technologies Used</h2>

- Firefox
- VMWare Workstation Pro

<h2>Operating Systems Used </h2>

- Linux 6.18

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Visit Wazuh's homepage on a VM and copy and paste the download installation script into your VM's terminal
- Step 2: Use the credentials Wazuh provides after the download is complete to access Wazuh's web interface through the IP address
- Step 3: Create a virtual machine (VM) and place it into the previously created resource group
- Step 4: Take the VM's public IP address, and access the VM through Remote Desktop Connection

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/sU1iZsW.png" height="80%" width="80%" alt="Step 1"/>
</p>
<p>
First, visit the Wazuh homepage to find the installation assistant. Go to "wazuh.com --> Install --> Quickstart". Scroll down until you see the installation assistant. Copy and paste it into the terminal on your VM. 
<br />

<p>
<img src="https://i.imgur.com/CFF9aii.png" height="80%" width="80%" alt="Step 2"/>
</p>
<p>
This may not come up, but if you are having issues pasting the script into your VM's terminal, follow these steps. First, run the command "sudo bash". This gives you root privilege access to the system. After entering your password, run "sudo apt install open-vm-tools", then enter "y". This installs the open-source version of VMware tools in a Linux VM, which will also allow you to copy and paste directly into the terminal. 
<br />
