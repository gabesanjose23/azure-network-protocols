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

<h2>Actions and Observations</h2>

<p>
<img src="Screenshot 2025-02-11 173108.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 1- We need to make a Windows virtual machine,Linux virtual machine and a Ubuntu server 20.04.They also all need to be on the same network.
</p>
<br />

<p>
<img src="Screenshot 2025-02-11 181421.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 2- Login on the Window machine by searching the remote connect and typing in the username and public IP address set to the virutal machine.Then go onto Microsoft Edge and search up www.wireshark.org.
</p>
<br />

<p>
<img src="Screenshot 2025-02-11 181924.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 3- Install it ,accept the terms of services,then search up the app and open it. 
</p>
<br />

<p>
<img src="Screenshot 2025-02-11 182304.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 4- Open up the app and if you see ethernet with the line being draw this shows it's active click on the top left shark fin(colored blue).
</p>
<br />

<p>
<img src="Screenshot 2025-02-11 182424.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 5- Here you can see all the outgoing and incoming packets you can also stop Wireshark with the red or reset it with the green fin.
</p>
<br />

<p>
<img src="Screenshot 2025-02-11 182841.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 6- Here I test out the connection to the machine by going into powershell and typing in the command (ping 8.8.8.8) .As you can see it will appear on wireshark.
</p>
<br />

<p>
<img src="Screenshot 2025-02-11 183345.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 7- Here I am going to set a rule on the firewall for the network to block incoming traffic from the ICMP.You can configure this by going into the azure portal ,navigating into the Linux VM and going into the network setting.
</p>
<br />

<p>
<img src="Screenshot 2025-02-11 183532.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 8- Here are the setting I put to block traffic from the ICMP which I put in the command (ping 8.8.8.8 -t)this way it will continuously ping.
</p>
<br />

<p>
<img src="Screenshot 2025-02-11 184445.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 8- As you can see it says request timed out.Any time it tries to ping it will drop the packet this is because the rule that is set on the firewall is working.
</p>
<br />


<p>
<img src="Screenshot 2025-02-11 184622.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Step 9- You can also add search filters like the packet number, the time it was received,what protocol,IP address,etc.In this example you can see I add a DNS filter and it will only show me domain names I searched for such as Disney and Microsoft Edge.
</p>
<br />
