<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Our Virtual machines
- Observe ICMP Traffic
- Configure Firewall/Network Security Group
- Observe SSH Traffic

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/BMluRZT.png"/>
</p>
<p>Created a Resource Group and deployed a Windows 10 Virtual Machine (VM)within it. During the VM setup, allowed the creation of a new Virtual Network (VNet) and Subnet, then proceeded to create a Linux (Ubuntu) VM within the same environment.
</p>
<br />

<p>
<img src="https://i.imgur.com/QuNPIzQ.png"/>
  <img src="https://i.imgur.com/EaGhVBn.png"/>
</p>
<p>Installed Microsoft Remote Desktop, connected to the Windows 10 VM, and set up Wireshark to capture ICMP traffic. Retrieved the private IP address of the Ubuntu VM, pinged it from the Windows 10 VM while monitoring traffic in Wireshark, and then tested internet connectivity by pinging a public website.
</p>
<br />

<p>
<img src="https://i.imgur.com/N8lKA0m.png"/>
  <img src="https://i.imgur.com/ZICzNGR.png"/>
</p>
<p>Initiated a continuous ping from the Windows 10 VM to the Ubuntu VM and monitored the ICMP traffic in Wireshark. Disabled inbound ICMP traffic in the Ubuntu VM's Network Security Group, observed the interruption in Wireshark and the command line, then re-enabled ICMP traffic and confirmed the ping responses resumed.
</p>
<br />

<p>
<img src="https://i.imgur.com/Lrp6eHj.png"/>
</p>
<p>Logged back into the Windows 10 VM, started a Wireshark packet capture, and filtered for SSH traffic. Used PowerShell to SSH into the Ubuntu VM via its private IP address, entered login credentials, observed the SSH traffic in Wireshark, and then exited the session by typing exit.
</p>
<br />
