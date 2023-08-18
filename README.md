<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>



Step by-step guide on how to observe network traffic to and from Azure Virtual Machines using Wireshark and experiment with Network Security Groups (NSGs):

Note: Before proceeding with the steps, make sure you have a Microsoft Azure subscription and access to the Azure portal.

Step 1: Create a Resource Group
- Log in to the Azure portal.
- Navigate to the Resource Groups page.
- Click on "Add" to create a new resource group.
- Provide a name, select the desired region, and click on "Review + create" to create the resource group.

Step 2: Create a Virtual Machine (Windows)
- Navigate to the Virtual Machines page.
- Click on "Add" to create a new virtual machine.
- Select the desired region and resource group created in Step 1.
- Choose the Windows operating system image.
- Configure the virtual machine settings, such as size, authentication, and networking.
- Click on "Review + create" and then "Create" to create the virtual machine.

Step 3: Create a Virtual Machine (Ubuntu)
- Follow the same steps as in Step 2, but choose the Ubuntu operating system image instead.

Step 4: Observe ICMP Traffic
- Remote into the Windows virtual machine using Remote Desktop.
- Install Wireshark on the Windows virtual machine.
- Open Wireshark and filter for ICMP traffic.
- Retrieve the private IP address of the Ubuntu virtual machine.
- Ping the Ubuntu virtual machine from the Windows virtual machine and observe the ping requests and replies in Wireshark.
- Ping a public website (e.g., www.google.com) and observe the traffic in Wireshark.
- Initiate a perpetual/non-stop ping from the Windows virtual machine to the Ubuntu virtual machine.
- Disable incoming (inbound) ICMP traffic in the Network Security Group of the Ubuntu virtual machine and observe the ICMP traffic being denied in Wireshark.
- Re-enable ICMP traffic in the Network Security Group and observe the ICMP traffic in Wireshark again.
- Stop the perpetual ping activity.

Step 5: Observe SSH Traffic
- Filter for SSH traffic in Wireshark.
- SSH into the Ubuntu virtual machine from the Windows virtual machine using its private IP address.
- Type commands (e.g., ls, pwd) into the SSH connection and observe the SSH traffic in Wireshark.
- Exit the SSH connection.

Step 6: Observe DHCP Traffic
- Filter for DHCP traffic in Wireshark.
- From the Windows virtual machine, attempt to issue a new IP address using the command "ipconfig /renew".
- Observe the DHCP traffic in Wireshark.

Step 7: Observe DNS Traffic
- Filter for DNS traffic in Wireshark.
- From the Windows virtual machine's command line, use nslookup to query the IP addresses of google.com and disney.com.
- Observe the DNS traffic in Wireshark.

Step 8: Observe RDP Traffic
- Filter for RDP traffic in Wireshark using the filter "tcp.port==3389".
- Observe the continuous stream of RDP traffic.
- Note that this constant traffic is due to the RDP protocol's live stream feature.

Step 9: Clean Up Your Azure Environment
- Close the Remote Desktop connection.
- Delete the Resource Group(s) created at the beginning of the tutorial to avoid additional charges.
- Verify the deletion of the Resource Group(s) to ensure they are properly removed.

That's it! You have now successfully observed various network traffic to and from Azure Virtual Machines using Wireshark and experimented with Network Security Groups. Make sure to follow the steps carefully and clean up your Azure environment to avoid any unwanted charges.
