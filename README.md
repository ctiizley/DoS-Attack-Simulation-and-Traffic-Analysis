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

Command: hping3 -S -p 80 ZYWIN01 --faster

A high volume of SYN packets was sent without completing the handshake, creating half open connections.
<br/>
 <h2>Observation </h2>

- <b>Large number of SYN packets visible in Wireshark</b>
- <b>Server responded with SYN-ACK packets</b>
- <b>Connection resources became strained</b>

<p align="center">
<img src="https://i.imgur.com/6luSwHK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="left">
ICMP Flood (Layer 3) 

 Command: ping -f -s 65500 ZYWIN01
 
Continuous ICMP traffic was used to consume network bandwith.
<br/>
 <h2>Observation </h2>

- <b>Large number of SYN packets visible in Wireshark</b>
- <b>Server responded with SYN-ACK packets</b>
- <b>Connection resources became strained</b>

<p align="center">
<img src="https://i.imgur.com/6luSwHK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="left">
UDP Flood (Layer 4) 

 Command: hping3 -flood --udp -d 60000 ZYWIN01
 
Large volumes of UDP packets were sent to trigger system responses.
<br/>
 <h2>Observation </h2>

- <b>High UDP traffic in Wireshark</b>
- <b>ICMP Destination Unreachable responses</b>
- <b>Increased bandwidth and CPU usage</b>

<p align="center">
<img src="https://i.imgur.com/6luSwHK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 <p align="left">
Sloworis Attack (Layer 7) 

Command: slowloris -s 500 --sleeptime 5 ZYWIN01

Multiple incomplete HTTP request were sent to exhause server connections.
<br/>
 <h2>Observation </h2>

- <b>Incomplete HTTP headers observed</b>
- <b>Low bandwidth usage</b>
- <b>Web server became unresponsive</b>

<p align="center">
<img src="https://i.imgur.com/6luSwHK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 <p align="left">
System Impact
System performance was monitored during the attacks.
<br/>
 <h2>Observation </h2>

- <b>Increased CPU and network utilization</b>
- <b>Resource exhaustion depending on attack type</b>

<p align="center">
<img src="https://i.imgur.com/6luSwHK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h2> Comparative Analysis </h2>

- <b>TCP SYN Flood → targets connection state (Layer 4)</b>
- <b>ICMP Flood → targets bandwidth (Layer 3)</b>
- <b>UDP Flood → targets bandwidth and CPU (Layer 4)</b>
- <b>Slowloris → targets application resources (Layer 7)</b>

<h2> Key Takeaways </h2>

- <b>Different DoS attacks impact different system resources</b>
- <b>Not all attacks require high bandwidth to be effective</b>
- <b>Packet analysis tools help identify attack behavior</b>
- <b>Monitoring tools are critical for detecting abnormal activity</b>


<h2>Skills Demonstrated</h2>

- <b>Network traffic analysis (Wireshark)</b>
- <b>Packet crafting and flood simulation</b>
- <b>System performance monitoring</b>
- <b>Differentiating attack types</b>

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
