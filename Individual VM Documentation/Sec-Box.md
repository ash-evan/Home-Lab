<h1> Purpose </h1>
The Security Box is a dedicated server for security services. It is used for centralized log management and running security tools, like Wazuh for monitoring clients. Having a dedicated server for this ensures these processes are isolated and resource-intensive processes will not interfere with critical operations on other servers. 
Using Wazuh, the box pulls Security and Application logs from the Windows Client and DC, and pulls auth.log, secure log, and audit.log from the Linux client. This provides logs and allows for intrusion detection mechanisms, XDR, etc. 

<br /> <br />

<h1>Services</h1>
To connect to AD, the Samba Winbind method was used. For this, the following additional modules were installed: winbind; libpam-winbind; libnss-winbind; krb5-config; samba-dsdb-modules; samba-vfs-modules. 
Curl was installed to help with installation of Wazuh for pulling logs from agents, providing intrusion detection, etc. 

<br /> <br />

<h1>Troubleshooting</h1>
<h2> Wazuh Installation </h2>
When trying to install Wazuh, there were some issues with hung processes having locks on apt. I had to exit the installation, use 'ps aux | grep apt' to find the hung processes, and kill them. I then had to re-run the Wazuh installation with the -o flag on Bash to overwrite the partial installation. After a few tries, Wazuh successfully installed. 

<br /> <br />

<h1>Future Plans</h1>
In future, more devices will be connected as Wazuh agents, extending the visibility across the network. I will also configure detection rules to create an intrusion detection ability. This will then be tested as part of a simulated attack.
