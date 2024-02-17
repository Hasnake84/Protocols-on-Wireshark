# NSG-Wireshark
<p align="center">

</p>

<h1>Analyze traffic using Wireshark Windows Network Security Group(NSG)</h1>

<h2>Environment and Technologies Used</h2>

- Microsoft Azure (Virtual Machines in the same Virtual Network)
- Remote Desktop
- Command-Line Tools
- Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Objecgtives</h2>

- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic


<h2>Windows Network Security Group(NSG) Inbound Rule > ICMP traffic > Deny, observe</h2>

<a href="https://imgur.com/jrXFI5k"><img src="https://i.imgur.com//jrXFI5k.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/NmsguKS"><img src="https://i.imgur.com//NmsguKS.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/F4HzN1j"><img src="https://i.imgur.com//F4HzN1j.png" title="source: imgur.com" /></a>

<h2>Windows Network Security Group(NSG) Inbound Rule > ICMP traffic > Allow, observe</h2>

<a href="https://imgur.com/tZNTwlP"><img src="https://i.imgur.com//tZNTwlP.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/gFBxs9K"><img src="https://i.imgur.com//gFBxs9K.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/WQdexei"><img src="https://i.imgur.com//WQdexei.png" title="source: imgur.com" /></a>

<h2>ssh traffic generated by ssh login to VM</h2>

   - Filter on Wireshark: tcp.port==22

<a href="https://imgur.com/yj59W6H"><img src="https://i.imgur.com//yj59W6H.png" title="source: imgur.com" /></a>

 <h2>DNS traffic</h2>

   - Filter on Wireshark: udp.port==5355
 
 <a href="https://imgur.com/QCT6IOu"><img src="https://i.imgur.com//QCT6IOu.png" title="source: imgur.com" /></a>

 
 4.) We are going to want to retrieve the private IP address of our Ubuntu VM and then attempt to ping it from within our Windows 10 VM using wireshark. To ping the private IP address of the Ubuntu machine open CMD or Powershell on the Windows machine and type: ping 10.0.0.5 or whatever the private IP address is for your Ubuntu machine.
 
<p>
<img src="https://imgur.com/zmJzyne.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
<p>
<img src="https://imgur.com/pp4eZdK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 In either CMD or Powershell ping www.google.com and observe the traffic in wireshark.
 
5.) We then are going to initiate a non-stop ping from our Windows 10 VM to our Ubuntu VM.
 
6.) Open the Network Security Group of our Ubuntu machine and disable incoming (inbound) ICMP traffic. To disable incoming ICMP traffic click "Add" new rule and copy everything exactly from the picture. Once that is done you can create the rule and it will create automatically and show up as a new rule.
 
 <p>
<img src="https://imgur.com/r3dH3Yy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
<p>
<img src="https://imgur.com/qiSIrsX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 Now that we have disabled incoming ICMP traffic from VM2 if we go back to VM1 you can see the ping request is timing out. 
 
 7.) Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is using
Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working)
Stop the ping activity
 
 8.) The next thing we are going to do is Observe SSH Traffic.
 
 
 

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
  
  
