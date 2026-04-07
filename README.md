<h1>Denial-of-Service (DoS) Attack Simulation and Traffic Analysis</h1>

 

<h2>Description</h2>
This project simulates multiple Denial-of-Service (DoS) attack scenarios in an isolated lab environment to analyze their impact on network performance, system resources, and service availability.
The objective was to understand how different DoS attacks operate across OSI layers and how they affect bandwidth, connection state, and application behavior.

All testing was conducted on authorized virtual machines in a controlled environment.

<br />

<h2>Enviornment </h2>

- <b>Kali Linux</b>
- <b>Windows Server 2022 (target system)</b>
- <b>Isolated virrtual network</b>

<h2>Tools Used </h2>

- <b>hping3</b>
- <b>ping</b>
- <b>slowloris</b>
- <b>Wireshark</b>
- <b>Windows Task Manager</b>


<h2>Attack Simulations</h2>
TCP SYN FLood (Layer 4)
<p align="center">
A high volume of SYN packets was sent without completing the handshake, creating half-open connections.
<br/>
<img src="https://i.imgur.com/6luSwHK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<h2>Observation </h2>

- <b>Large number of SYN packets visible in Wireshark</b>
- <b>Server responded with SYN-ACK packets</b>
- <b>Connection resources became strained</b>

<p align="center">
<img src="https://i.imgur.com/6luSwHK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="left">
 ICMP Flood (Layer 3) <br/>
<p align="center">
  Continuous ICMP traffic was used to consume network bandwith.
<br/>
<img src="https://i.imgur.com/tV9KQIw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="left">
 Phase 3: Block Telnet (Port 23) <br/>
<p align="center">
Prevents plaintext credential exposure
<br/>
<img src="https://i.imgur.com/CqbdhEn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="left">
 Phase 4: Block SMB (Port 445) <br/>
<p align="center">
Estimated the operating system using TCP/IP fingerprinting based on network response behavior.
<br/>
<img src="https://i.imgur.com/BkUlKHD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br />
<p align="left">
 Phase 4: Block TFTP (Port 69)
<br/>
<p align="center">
Prevents unauthorized file transfers (no authentication/encryption)
<br/>
<img src="https://i.imgur.com/0i12zQ7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br />
<p align="center">
SMTP Configuration Restricted unencrypted SMTP and enforced secure email transmission
<br/>
<img src="https://i.imgur.com/fQK14Av.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h2> Security Improvements </h2>

- <b>Reduced attack surface</b>
- <b>Replaced insecure protocols with secure alternatives</b>
- <b>Implemented outbound filtering</b>
- <b>Maintained required services</b>

<h2> Skills Demonstrated </h2>

- <b>Firewall configuration</b>
- <b>Traffic filtering (inbound/outbound)</b>
- <b>Service enumeration</b>
- <b>Port-based security</b>
- <b>Risk-based decision making</b>


<h2>Ethical Statement</h2>
All activities were conducted in an isolated lab environment on authorized systems for educational and defensive security purposes only.
<br />
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
