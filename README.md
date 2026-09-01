<h1> README </h1>
This repo is the documentation for my home lab setup. 
<br /> <br />
<h2>Aims</h2>
I am a recent CyberSec graduate aiming for service desk or SOC roles. My aim with this project is to gain familiarity and real experience with building a small corporate network, configuring AD, and setting up security and device hardening, and have tangible proof.
<br /><br />
<h2>Setup</h2>
The lab currently consists of 7 VMs running in Oracle VirtualBox. They are all connected via their own NAT network. This allows the VMs to communicate with each other and access the Internet via the DC running DNS and DHCP services. Every device apart from Security Onion has its own domain account and is connected to the DC. Security Onion is kept separate from the domain so that investigations of malicious content can be done without risk to the domain. 
<br />
<img width="527" height="328" alt="Screenshot showing 7 VMs in VirtualBox" src="https://github.com/user-attachments/assets/960a7761-6006-4388-87c1-2c576889f310" />
<br />
<h2> Plans </h2>
I plan to use this small network to simulate attacks and perform investigations using Security Onion and the Wazuh logs. I will also work on hardening all of the devices appropriately and configuring policies in AD. 
