<h1> Purpose </h1>
The Win-Client-10 machine is intended to represent the several Windows clients which would be within a corporate environment. This allows for managing AD settings on a Windows client, configuring its security, and using it as part of offensive and defensive investigations. 

<br /> <br />

<h1> Services </h1>
Currently, the only non-base installation on the Windows machine is Wazuh, to allow connection to the Security Box for the ability to detect security events. It is part of the Windows group on Wazuh and sends its Security and Application logs to Wazuh. 

<br /> <br />

<h1> Troubleshooting </h1>
<h2> Version </h2>
Ideally, this would have been a Windows 11 client as most corporate environments will be running 11 due to the EOL for 10. However, my hardware lacks the necessary TPM 2.0 requirement to run Windows 11. Therefore, Windows 10 was the next best option. 
<br />
The next issue was trying to obtain a copy of Windows 10 to install as Microsoft doesn't seem to distribute it online anymore. Luckily, I have a Windows 10 installation on my home machine and was able to use the Windows Media Creation Tool to create a Windows 10 ISO using this host installation. 

<br /> <br />

<h2> Installation </h2>
I used VirtualBox to provision all of the VMs. When installing the Windows 10 ISO, the installation froze at 30% and even after waiting for a significant time, did not complete. I restarted the machine and the install restarted from 0. The installation again froze. I realized that changing between full screen mode and windowed mode helped to unfreeze the installation temporarily. I had to keep using this technique to unfreeze the installation until it finally completed. 

<br /> <br />

<h1> Future Plans </h1>
Once I have set up security detections, this machine will be used as part of simulated offensive and defensive activities. It can also be used on the DC to practice provisioning proper access controls and policies. 
