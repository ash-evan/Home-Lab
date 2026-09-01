<h1> Purpose </h1>
The Linux Client is intended to represent various Linux clients which may be part of a corporate network. It allows me to gain experience connecting a Linux machine to AD and implementing effective security controls on Linux. This client was also used to run an email poller script to communicate with the Mailhog service on the corporate server to simulate an email server running. 

<br /> <br />

<h1> Services </h1>
To connect to AD, the Samba Winbind method was used. For this, the following additional modules were installed: winbind; libpam-winbind; libnss-winbind; krb5-config; samba-dsdb-modules; samba-vfs-modules. This client also has the Wazuh agent installed for security monitoring. For the email poller script to run to pull new email intended for the client, the following modules were needed for the script to run: curl; jq. 

<br /> <br />

<h1> Troubleshooting </h1>
<h2> OS </h2>
Ubuntu 22.04 was chosen because it is compatible with connecting to Windows Server 2025. Ubuntu also has good compatibility for hardware and software, which would be necessary for a corporate environment. 

<br /> <br />

<h2> Connecting To AD </h2>
There are 2 main methods to connect a Linux client to Microsoft AD. The first is SSSD realmd method. This method was not compatible with Windows Server 2025 and Ubuntu 22.04 at the time of installation. Therefore, I used the Samba Winbind method. When trying to connect to AD, I found the DC's time was desynced and wrong by a few minutes meaning the client could not connect. Time de-syncs can be a common issue when running VMs as the hypervisor tries to sync the times while the devices are trying to sync themselves, creating conflicts. To fix this, I removed the VM guest time sync and restarted w32tm - the service which syncs dates and times for devices connected to the DC. This fixed the desync issue and allowed the Linux client to connect to the DC correctly. 
<br />
I had also forgotten to edit resolv.conf to add the DC as the DNS domain. This was a quick fix. 

<br /> <br />

<h2> Signing in to AD </h2>
When attempting to sign in to the account provisioned for this client on AD, the sign in was failing. Checking the account on the DC, the account was locked, causing the login failures. Unlocking the account fixed the issue and the client successfully signed in to the AD account. 

<br /> <br />

<h1> Future Plans </h1>
Once I have set up security detections, this machine will be used as part of simulated offensive and defensive activities. It can also be used on the DC to practice provisioning proper access controls and policies.
