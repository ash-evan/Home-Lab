<h1> Table of Virtual Machines </h1>

| VM Name | Hostname | OS | Processors | RAM | Storage | IP | Function |
|---------|----------|----|------------|-----|---------|----|----------|
| Windows-DC-2025 | Windows-DC-2025 (corp.soclab-dc.com) | Windows Server 2025 | 2 | 4096 MB | 50GB | 10.0.0.5/24 | Domain controller (DNS, DHCP, SSO) |
| Win-Client-10 | Win-Client-10 | Windows 10 | 2 | 4096 MB | 80 GB | 10.0.0.100/24 | Windows Workstation |
| Linux-Ubuntu-Client-22.04 | linux-client | Ubuntu 22.04 Desktop | 1 | 2048 MB | 80GB | 10.0.0.101/24 | Linux Workstation |
| Security Onion | security-onion | Security Onion | 1 | 2048 MB | 55 GB | 10.0.0.103/24 | Defense Tools |
| Corp-Serv | corp-serv | Ubuntu 22.04 Desktop | 2 | 4096 MB | 80 GB | 10.0.0.9/24 | Dedicated server. Mailhog |
| Email-Serv | email-serv | Ubuntu Server 22.04 | 1 | 2048 MB | 25 GB | 10.0.0.8/24 | Linux Email Server |
| Security-Box | security-box | Ubuntu 22.04 Desktop | 2 | 4096 MB | 80 GB | 10.0.0.10/24 | Wazuh. Security server |

<h2> Details of VM Setup </h2>
All of the machines are VMs run on Oracle VirtualBox. The aim with this network is to simulate a small corporate environment to gain experience with building and configuring a network, and setting up the security properly.  
<br /> <br />
Windows-DC-2025 is the domain controller for this network. All VMs except the Security Onion VM are connected to the DC. Security Onion is not connected for security reasons - so that this VM can be used for investigation without the risk of compromising all devices connected to the domain. 
<br /> <br />
Currently, the DC, Windows client, and Linux client are connected as Wazuh agents to the Security Box.
