<h1> Purpose </h1>
This device is the Windows Domain Controller for the domain. This is done to simulate a typical corporate environment where active directory is used to manage devices. The DC provides services like DNS, DHCP, and SSO to clients. A different account is provisioned for each client, and groups and policies can be managed from here. 

<br /> <br />

<h1> Services </h1>
The DC runs DNS, DHCP, and SSO services for the clients. Wazuh is also installed so it can send its Security and Application logs to the Sec-Box. Otherwise, this is a base Windows Server 2025 installation. 

<br /> <br />

<h1> Troubleshooting </h1>
The only issue with the DC so far has been the time de-sync issue preventing client connections, as described in Linux-Client.md. This was due to VirtualBox's guest time sync causing conflicting priorities for time data. Disabling this and restarting the w32tm service fixed the issue. 

<br /> <br />

<h1> Future Plans </h1>
I plan to configure policies, group permissions, and harden the DC. It will also be used as part of a simulated attack to test its security. 

