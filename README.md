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
- Various Network Protocols (ICMP, SSH, DHCP, DNS, RDP)
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

Getting started:

1.) First I have to create a resource group on Azure which will include two Virtual Machines (Windows 10 & Ubuntu)

2.) Remote into both the Virtual Machines(VM) with Remote Desktop Connection, if you are running a WindowsOS, or Microsoft Remote Desktop, if you are using macOS

3.) Download WireShark onto the Windows 10 Virtual Machine

4.) The following images will present how I observed the network traffic via WireShark.

<br/>
<p>
<img src="https://imgur.com/xB3LRcI.png" 
     </p>

This image is how I monitored the ICMP traffic between the two VM's (Windows & Ubuntu).

  1.) Retrieve the private IP address of the Ubunutu VM (in my case the private IP address was 10.0.0.5)

  2.) After retrieving the private IP address of the Ubuntu VM, I then connected to the Windows VM and pinged the private IP address of Ubuntu on the command prompt. 
  
 3.) The ping request and replies were then observerd in WireShark while the command line ping activitiy was monitored in the Windows 10 VM.
  
  Some context:
  Internet Control Message Protocol (ICMP) is a network protocol used for diagnostic and control purposes within IP networks. It is primarly utilized by network devices, such as routers, to communicate error messages and operational information regarding network connectivity. 
  
<br/>
 <p>
   <img src="https://imgur.com/N2ilsoq.png"
        </p>
   
        
