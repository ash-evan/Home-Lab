<h1> Purpose </h1>
The corporate server is a jumpbox and has containers for running services like Mailhog - simulating an email service. These services would ideally run on separate VMs but this would require more resources to run than is realistic for a home lab so the containers mimic the desired setup. This server allows clients to access various services. 

<br/> <br />

<h1> Services </h1>
To connect to AD, the Samba Winbind method was used. For this, the following additional modules were installed: winbind; libpam-winbind; libnss-winbind; krb5-config; samba-dsdb-modules; samba-vfs-modules. This client also has the Wazuh agent installed for security monitoring.
<br /> <br />
The services are run on containers. Docker was installed for container management. For this, the following modules were installed: ca-certificates; curl; docker-ce; docker-ce-cli; containerd.io; docker-buildx-plugin; docker-compose-plugin. 
Mailhog was then installed on a container. For this, the Mailhog image was pulled from Docker. 

<br/> <br />

<h1> Troubleshooting </h1>
<h2> Docker Install </h2>
When trying to install Docker, accessing the website from the corp serv was showing invalid certs which meant that the Docker keys were not trusted during installation. Checking on my host system, the site had valid certificates. Trying to access any site on any VM caused warnings for invalid certificates. I found this was because the anti-malware on my host system, Kaspersky, interferes with the certificate chain so it can inspect encrypted connections. Because the VMs weren't aware of this, it was causing errors in the certificate chain. 
After some digging through the Kaspersky settings, I found the issue was regarding scanning encrypted connections. I changed this setting to prevent the certificate chain from being invalidated on the VMs. This meant the Docker keys were then trusted and the install completed correctly. 

<br/> <br />

<h1> Future Plans </h1>
More services will be set up in Docker containers in future to increase the utility of the corporate network. I will also harden this server, as it is a jumpbox and should have controls in place. 
