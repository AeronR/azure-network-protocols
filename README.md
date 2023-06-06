<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Inspecting Traffic Between Azure Virtual Machines</h1>

In this document, I will be inspecting various network traffic between two Azure Virtual Machines using WireShark.

Observing and understanding Network Protocol traffic is quite imporant and is used for multiple reasons such as:

1. Troubleshooting network issues
2. Identifying security vulnerabilities and detecting attacks
3. Optimizing network performance
4. Developing and testing protocols
5. Monitoring networking activity and establishing baselines
6. Education purposes and learning about networking

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools (ping, ipconfig) 
- Various Network Protocols (ICMP, SSH, DHCP, DNS, TCP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>Objective</h2>

Observe the various network protocol traffic which includes:

- ICMP (Internet Control Message Protocol)
- SSH (Secure Shell)
- DHCP (Dynamic Host Configuration Protocol)
- DNS (Domain Name System)
- RDP (Remote Desktop Protocol)

<h2>Actions and Observations</h2>

<p>
Getting started:

1.) First I have to create a resource group on Azure which will include two Virtual Machines (Windows 10 & Ubuntu)

2.) Remote into both the Virtual Machines(VM) with Remote Desktop Connection, if you are running a WindowsOS, or Microsoft Remote Desktop, if you are using macOS

3.) Download WireShark onto the Windows 10 Virtual Machine

4.) The following images will present how I observed the network traffic via WireShark.
</p>

<h3>ICMP Traffic</h3>  

<p>
<img src="https://imgur.com/xB3LRcI.png" 
     </p>

 <p>
 How to display ICMP traffic:
    
 1.) Retrieve the private IP address of the Ubuntu VM (in my case the private IP address was 10.0.0.5)

 2.) After retrieving the private IP address of the Ubuntu VM, I then connected to the Windows VM and pinged the private IP address of Ubuntu on the command prompt using the command like "ping (followed by the IP address)".
  
 3.) The ping request and replies are then displayed in WireShark while the command line ping activitiy was monitored in the Windows 10 VM.
  
Some context:
  
Internet Control Message Protocol (ICMP) is a network protocol used for diagnostic and control purposes within IP networks. It is primarly utilized by network devices, such as routers, to communicate error messages and operational information regarding network connectivity. 
</p>     

<h3>SSH Traffic</h3>

<p>
<img src="https://imgur.com/cWYhgkr.png"
</p>

<p>     
How to display SSH Traffic:
     
1.) On the Windows 10 VM, open WireShark and filter for SSH traffic.
 
2.) While on the Windows 10 VM, open the command prompt and SSH into the Ubuntu VM's private IP (in my case it was 10.0.0.5)
    
3.) Once I logged into the Ubuntu VM through the Windows VM command prompt, WireShark will then display the SSH traffic.
    
Some context:

Secure Shell(SSH) is a network protocol that provides secure remote access to systems over an unsecured network.
     
The primary focus of SSH is to enable users to securely log into remote systems and execute commands remotely. It establishes a secure encrypted channel between the client and the server, protecting the confidentiality and integrity of the communication. 
</p>     
 
<h3>DHCP Traffic</h3>

<p>
<img src=https://imgur.com/0wfF21K.png"
</p>
                                          
<p>
How to observe DHCP Traffic:

1.) Again on the Windows VM, open WireShark and filter for DHCP traffic.

2.) While on the Windows VM, issues your machine a new IP address by opening the command prompt and typing it the command line "ipconfig /renew" which will then restart your VM and issue a new IP address.

3.) Once the IP address has been renewed, WireShark will then start displaying the DHCP traffic. 
 
Some Context: 
                                                                                                                                                
Domain Host Configuration Protocol is a network protocol used to automatically assign IP addresses and other network configuration settings to devices on a  network. It simplifies the process of IP address allocation and configuration manangemnt in a network enviornment. 
</p>

<h3>TCP Traffic</h3>                                                                                                                                               
<p>
<img src=https://imgur.com/pGzBryt.png"
</p>
    
<p>
1.) On Windows 10 VM, open WireShark and filter for "tcp.port == 3389".
     
2.) WireShark will then display TCP traffic. 
     
Some Context:

Transmission Control Protocol(TCP) is a protocol used for sending and recieving data over the internet. It ensures the data is delivered realiably and in the correct order. 
</p>

   

          
                                                                                                                                                
                                                                                                                                                
