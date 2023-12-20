<h1>Building a SOC + Splunk in Linode (Live Traffic)</h1>

![splunk10](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/8f0c8294-2c26-4c18-8c19-bb25a5a3b4a2)


<h2>Introduction</h2>
In this project I have tried to simulate a live DDOS and Bruteforce attack on Web server and monitor the attack with a powerful tool Splunk. I have created Splunk server and Web server in Linode and a local Kali machine to attack those two servers. I then monitored the attack, analyze logs, created alerts and used Splunk SPL to further analyze the attack scenario as well as a beautiful dashboard for viewing the attack summary.
<br />

<h2>Environments Setup </h2>

To create a <b>SIEM environment</b>, 2 virtual machines were created via Linode and 1 virtual machine via virtualbox.<br><br>
The first machine is a <b>Splunk Server</b> running in port 8000 and listening port on 9997.<br><br>
The second machine is a <b>Web Server</b> running <b>Apache2, MySql, SSH</b> and a <b>Wordpress</b> site. This machine is installed and configured with Splunk universal forwarder to send logs to Splunk Server to then be indexed and monitored in real time.<br><br>
The third machine is a <b>Kali Linux</b> hosted in a local environment to simulate DDOS and Bruteforce attack to the Web Server using various tools and scripts.

<h2>Program walk-through:</h2>

<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
