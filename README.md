<h1>Capturing Remote Desktop Protocol (RDP) Traffic in Wireshark on Azure VMs</h1>
<h2>Objective</h2>

 - Guide users through establishing a Remote Desktop Protocol (RDP) session between Azure VMs, capturing the RDP traffic in Wireshark, and understanding how remote desktop connections appear in network traffic.



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computers)
- Remote Desktop
- Powershell
- Command-Line Tools
- Network Protocol RDP
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2)
- Ubuntu Server 22.04


<h2>What is RDP (Remote Desktop Protocol)?</h2>

 - RDP is a Microsoft protocol that enables users to remotely control a Windows computer as if they were physically in front of it.
 - It is commonly used for IT support, remote work, and system administration. RDP allows keyboard and mouse inputs to be sent remotely, while the screen display is streamed back to the user.
 - Port Number: 3389 (TCP & UDP)
 - In Wireshark: Filtering for rdp will show RDP session traffic. While the actual screen data is encrypted, monitoring RDP traffic can help detect unauthorized remote access attempts.



<h2>Actions and Observations</h2>
<h3>Step 1 - Filter for RDP Traffic in Wireshark</h3>

 - [ ] Open **Wireshark** and start a new **packet capture**.
 - [ ] In the **Wireshark filter bar**, type:
	
		 tcp.port == 3389
 - RDP traffic operates over  **TCP port 3389**, so this filter will isolate only RDP-related packets.

<h3>Step 2 - Observe the RDP Traffic in Wireshark</h3>

 - You should immediately see a  **constant stream of RDP traffic**  appearing in Wireshark — even if you aren’t doing anything within the remote session.
 - The traffic will include:
	 - **Data packets**  representing screen updates
	 - **Input packets**  for mouse movements and keyboard strokes
	 - **Keep-alive packets**  to maintain the connection

<img width="1512" alt="Step 8a - RDP" src="https://github.com/user-attachments/assets/4178fabd-683a-4f19-bbc2-d48b6cf5222a" />

<h2>Summary & Significance</h2>

<h3>What You Did</h3>

 - [ ] Used  **Wireshark**  to capture and filter RDP traffic (TCP port 3389).
 - [ ] Established a remote desktop session between your local machine and the Windows 10 VM.
 - [ ] Observed the continuous RDP packet stream in Wireshark.

<h3>Why This Matters</h3>

 - **RDP is widely used**  for remote administration, support, and access to virtual machines — understanding how it works is essential for system administrators and IT professionals.
 - **Constant traffic is normal**  for RDP — recognizing this helps differentiate between normal behavior and potential issues like network congestion or malicious activity.
 - **Wireshark enables RDP troubleshooting**  – if the connection is laggy or unstable, analyzing packet flow in Wireshark can help identify problems (like packet loss or high latency).
 - **Monitoring RDP traffic**  can also help spot unauthorized remote access attempts.
 - By completing this tutorial, you’ve gained practical experience with **capturing RDP traffic**, **understanding why it’s constant**, and **recognizing the structure of a live RDP session**.

