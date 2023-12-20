<h1>Building a SOC + Splunk in Linode (Live Traffic)</h1>

![splunk10](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/8f0c8294-2c26-4c18-8c19-bb25a5a3b4a2)


<h2>Introduction</h2>
In this project I have tried to simulate a live DDOS and Bruteforce attack on Web server and monitor the attack with a powerful tool Splunk. I have created Splunk server and Web server in Linode and a local Kali machine to attack those two servers. I then monitored the attack, analyze logs, created alerts and used Splunk SPL to further analyze the attack scenario as well as a beautiful dashboard for viewing the attack summary.
<br />

<h2>Attack Summary Dashboard</h2><br>

![splunk6](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/63596a01-552b-429e-ade1-f1246579e31e)

<h2>Environments Setup </h2>

To create a <b>SIEM environment</b>, 2 virtual machines were created via Linode and 1 virtual machine via virtualbox.<br><br>
The first machine is a <b>Splunk Server</b> running in port 8000 and listening port on 9997.<br><br>
The second machine is a <b>Web Server</b> running <b>Apache2, MySql, SSH</b> and <b>Wordpress</b>. This machine is installed and configured with <b>Splunk universal forwarder</b> to send logs to Splunk Server to then be indexed and monitored in real time.<br><br>
The third machine is a <b>Kali Linux</b> hosted in a local environment to simulate DDOS and Bruteforce attack to the Web Server using various tools and scripts.

<h2>DDOS Attack</h2>
I used a script found on github to simulate DDOS attack from my Kali machine, the Splunk server generated an event for this attack. I used SPL to list the source IP and location of the attack as shown below:<br><br>

![splunk1](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/e1f358c9-b651-403f-8b17-1c9fd70be964)<br><br>

![splunk2](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/29775273-c794-49d5-a697-04cec60fe9c4)<br><br>

![splunk3](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/525e6a04-8a47-45dd-b4c6-3cc1526d1bcd)<br><br>

<h2>Bruteforce Attack</h2>
I used a tool <b>hydra</b> from Kali Linux to simulate <b>Bruteforce</b> attack on Wordpress login page. I tried to analyze where the login was performed from and the Wordpress uri path.<br><br>

![splunk4](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/7bf8f946-71b2-4be6-9646-419b1b62d5f0)<br><br>

![splunk5](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/3f48befc-37d5-43d0-b155-4c6ebc140dec)<br><br>

<h2>Alert</h2>
Splunk has a feature to generate alert for any activity through SPL. I generated an alert for both DDOS and Bruteforce attack in real time.<br><br>

![splunk8](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/bcbdf693-3c4e-4cac-93a9-0569e8c116c3)<br><br>

![splunk7](https://github.com/prasannashah1/Splunk-SOC/assets/28432698/9d2febfd-8bd9-4b08-b495-ee092838e1b9)<br><br>

<h2>Conclusion</h2>
This project demonstrated the real time Cyber attack scenario on a Server. Splunk server and Web server was deployd on cloud through Linode. Splunk was used to generate events logs and alerts from the web server whenever the web server was attacked. Also the attack scenario was depicted in a statistics and grpahical view through Splunk SPL.

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
