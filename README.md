<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, DNS, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)
- Ubuntu Server 22.04

<h2>High-Level Steps</h2>

- Create 2 Virtual machines (VMs)
- Download Wireshark
- Observing ICMP traffic
- Observing SSH traffic
- Observing DNS traffic

<h2>Breakdown</h2>

- In this first section I will create 2 Virtual Machines (VMs), in this image we have built 2 different VMs 1 for linux in "Ubuntu Server" and the other for windows client in "Windows 10".

![image](https://github.com/user-attachments/assets/71d3c255-a7fe-4330-a0c6-e23d93bb1c49)

- In this second section I will be downloading Wireshark in our "windows client", Wireshark is a free and open-source packet analyzer used for network troubleshooting, analysis, and network monitoring, this first image shows where we downloaded the tool. After installing wireshark we open the tool and have a visual of network traffic which is what is shown in the second image.

![Screenshot 2024-12-26 174846](https://github.com/user-attachments/assets/d648b62e-8a42-4f3a-8a10-3ad49fdca57d) ![image](https://github.com/user-attachments/assets/673f397a-838f-48eb-8b6d-22b3ac528f64)

- In this third section I will attempt to ping "linux vm" and observe the traffic, I first obtained the private IP for the "linux vm" then I pinged "linux vm" using powershell from the "windows client", the ping was successful, which is what the first image below is showing. The second image is showing wireshark capturing the filtered traffic "ICMP" which is the protocol for the command ping, the ping command is a network utility used to test the connectivity between two devices on a network. 

![image](https://github.com/user-attachments/assets/aa008fd7-0b76-49c3-bd8d-1725bf4b7220) ![image](https://github.com/user-attachments/assets/9e7d25a8-104b-4a4c-ad49-a167a0351aee)

- In this fourth section I will be connecting to "linux vm" through powershell using SSH and observe traffic, in this first picture I have successfully connected to "linux vm" through powershell using SSH. In the second image you can see that I have filtered wireshark to capture only SSH traffic and wireshark is capturing all keystrokes that are happening live through SSH.

![image](https://github.com/user-attachments/assets/f5e91e95-844e-4727-a650-5658a6efe1c0) ![image](https://github.com/user-attachments/assets/0948a3ee-741d-42b8-ba88-b677317a6d33)

- In this fifth section I just filter wireshark to DNS and I start getting traffic that is happening in the background

![image](https://github.com/user-attachments/assets/efe81713-fcf4-4889-a3b6-627cf02a9ff1)
