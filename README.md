<p align="center">
<img src="https://i.imgur.com/Y6kPrX0.jpeg" alt="SIEM Logo"/>
</p>


<h1>Setup and Deployment of Security Information and Event Management (SIEM) and Extended Detection and Response (XDR) tools on Linux VM</h1>
This tutorial outlines the setup and deployment of Wazuh's combined SIEM and XDR tool on a Linux virtual machine.<br />

<h2>What are SIEM and XDR tools?</h2>
A Security Information and Event Management, or SIEM, is a tool that assists organizations in recognizing potential security threats before they happen. They include log management, incident monitoring and security alerts, event analytics, and compliance management and reporting. SIEM tools are of great use to organizations for real-time threat recognition and boosting organizational efficiency. A SIEM is a necessity for any SOC analyst. 

Extended detection and response, or XDR, takes data from all areas of an organization's environment: IAM, email, network, cloud, endpoints, etc. It brings all of that information into a single platform, sorts it into a digestible format, to assist organizations in detecting and responding to threats. 

The main difference between the two is that SIEM uses broad log management to alert security teams to any suspicious activity on a network, while XDR can detect, investigate,  and respond. SIEM tools are better used for compliance and visibility across a network, while XDR is excellent for threat hunting and rapid response. 

<h2>Environments and Technologies Used</h2>

- Firefox
- VMware Workstation Pro
- Wazuh SIEM and XDR tool

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

<p>
<img src="https://i.imgur.com/VzBgbvt.png" height="80%" width="80%" alt="Step 3"/>
</p>
<p>
Now, paste the installation assistant into the terminal, and allow Wazuh to finish the process. After it has finished installing, scroll to the bottom of the process and save the username and password it provides.
<br />

<p>
<img src="https://i.imgur.com/U9gkdlS.png" height="80%" width="80%" alt="Step 3"/>
</p>
<p>
Next, enter "ip a" into the terminal. This command will give you several bits of information, but the most important one is the IP address you will need to use to access Wazuh's system. You will find it in the second section of the information. 
<br />

<p>
<img src="https://i.imgur.com/qHMvXsM.png" height="80%" width="80%" alt="Step 3"/>
</p>
<p>
From here, copy and paste the IP address into the search bar in a web browser and allow it to take you to the Wazuh website. A message will pop up and inform you that the certificate is not from a trusted authority. This is expected, and there is no risk posed to you moving forward. After you input your username and password, congratulations! You have successfully set up the Wazuh SIEM and XDR tool! Now, to deploy some agents. 
<br />

<p>
<img src="https://i.imgur.com/3zMBHCg.png" height="80%" width="80%" alt="Step 3"/>
</p>
<p>
At the top left of the dashboard, click "+ Deploy new agent". A new window will open, with different options for the agent depending on the system you plan to deploy it to. First, we need to select the package to download and install on our system. Since this example is using a Kali Linux VM, "DEB amd64" is the appropriate choice. For the server address, copy and paste the IP address in the search bar that you used to access this web browser. Then, choose a name for the agent (just make sure it is unique, and know that it cannot be changed). Now, Wazuh will have created commands for you to run.
<br />

<p>
<img src="https://i.imgur.com/Oxxwv4o.png" height="80%" width="80%" alt="Step 3"/>
</p>
<p>
To start the agent, you need to create a separate VM. You can clone your current VM to make this easier. Once you have, input the command to download and install the Wazuh agent. Following that, input the command to start the agent. 
<br />

<p>
<img src="https://i.imgur.com/c1zc3aS.png" height="80%" width="80%" alt="Step 3"/>
</p>
<p>
Now that the first agent is deployed, refresh the SIEM's dashboard to see the agent pop up. To access it, click on "Active (1) --> [your agent title]". From here, poke around. This SIEM tool offers numerous functions, and this tutorial will only cover a few of them. First, we'll examine how activity on the agent shows up on the dashboard. 
<br />

<p>
<img src="https://i.imgur.com/ZGqQJdU.png" height="80%" width="80%" alt="Step 3"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/khL8a6g.png" height="80%" width="80%" alt="Step 3"/>
</p>
<p>
On the VM the agent is active on, enter "whoami" or any other simple command into the computer's terminal. Head back to the other VM and refresh Wazuh's dashboard. Here, you will see activity noted immediately, with the MITRE ATT&CK framework, vulnerability detection, compliance, events count evolution, etc. Additionally, if you head to "Explore --> Discover", you can find all of the logs coming into the SIEM. Congratulations! You have successfully set up Wazuh's SIEM tool and deployed an agent to help monitor your network.  
<br />
