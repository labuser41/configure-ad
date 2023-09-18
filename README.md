<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services


<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Resources in Azure
- Created two Virtual Machines 
- Edited the IP Private Address settings 
- Ensured Connectivity between the client and Domain Controller
- Installed Active Directory 

<h2>Deployment and Configuration Steps</h2>

<h4>Created the Domain Controller VM (Windows Server 2022) named “DC-1”. Created the Client VM (Windows 10) named “Client-1”. Ensured that both VMs were on the same Vnet.</h4>                                  
<img src="https://github.com/labuser41/configure-ad/assets/144741692/ae79624b-46e0-4aec-b934-13e773164cba">


<img src="https://github.com/labuser41/configure-ad/assets/144741692/67ec8426-a158-4653-9fc4-d12af2515940">
<h4>After confirming the same vnet, I set the Domain Controller’s NIC Private IP address to be static in order to keep the IP address from changing. </h4> 
</p>
<br />

<img src="https://github.com/labuser41/configure-ad/assets/144741692/e3aa0a8e-2467-4ef2-bce7-fd0e8a6cb2cd">

<h4>I logged in to Client-1 with Remote Desktop and pinged DC-1’s private IP address with ping -t <ip address> (perpetual ping). </h4>
<img src="https://github.com/labuser41/configure-ad/assets/144741692/60f786d2-006d-4be2-a85c-a0abc274a3a4">


<h4>The ping is timing out due to the firewall. In order to allow the traffic, I logged into the Domain Controller and enabled ICMPv4 in on the local windows Firewall. </h4>
<img src="https://github.com/labuser41/configure-ad/assets/144741692/fef99f65-3663-407b-85dc-8b5df1d73bbc">

<img src="https://github.com/labuser41/configure-ad/assets/144741692/8d8cace6-58a2-4fef-9a5b-60595ab249c9">
<img src="https://github.com/labuser41/configure-ad/assets/144741692/d3697258-bb5e-4bb2-b0b4-2e613b1d4681">



<p>
 <h4>Now the ping is successful.</h4> 
<img src="https://github.com/labuser41/configure-ad/assets/144741692/1c25db72-6816-4858-b170-83034ed354f0">

<h4>Used Service Manager within the Remote Desktop to install Active Directory.</h4> 
<img src="https://github.com/labuser41/configure-ad/assets/144741692/83420826-d5f1-4559-b329-b7a2eb52d167">
<h4>Created a new employee named “Jane Doe” with the username of “jane_admin” and added jane_admin to the “Domain Admins” Security Group.</h4>
<img src="https://github.com/labuser41/configure-ad/assets/144741692/87a4653c-5913-49c0-b0d3-f697dcf84e42">


