<h1>Capturing Remote Desktop Protocol (RDP) Traffic in Wireshark on Azure VMs</h1>
Objective: Guide users through establishing a Remote Desktop Protocol (RDP) session between Azure VMs, capturing the RDP traffic in Wireshark, and understanding how remote desktop connections appear in network traffic.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Powershell
- Various Command-Line Tools
- Network Protocol ICMP
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2)
- Ubuntu Server 22.04


<h2>Actions and Observations</h2>

<br>


<h3>Step 1 - RDP (Remote Desktop Protocol)</h3>
•	RDP is a Microsoft protocol that enables users to remotely control a Windows computer as if they were physically in front of it.<br>
•	It is commonly used for IT support, remote work, and system administration. RDP allows keyboard and mouse inputs to be sent remotely, while the screen display is streamed back to the user.<br>
•	Port Number: 3389 (TCP & UDP)<br>
•	In Wireshark: Filtering for rdp will show RDP session traffic. While the actual screen data is encrypted, monitoring RDP traffic can help detect unauthorized remote access attempts.<br>

<img width="1512" alt="Step 8a - RDP" src="https://github.com/user-attachments/assets/4178fabd-683a-4f19-bbc2-d48b6cf5222a" />

