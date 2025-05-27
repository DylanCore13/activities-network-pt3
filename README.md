# activities-network-pt3


![image](https://github.com/user-attachments/assets/4ed2242a-809c-45a7-9fab-4091aef6f850)    ![image](https://github.com/user-attachments/assets/8ad90810-eb97-4e8a-877a-8c34541b3594)






<h2>(Configuring a Firewall [Network Security Group])</h2>




  
- Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM
    - Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic
    - Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity
    - Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is
    - Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working)
    - Stop the ping activity

<h2>(Observe SSH Traffic)</h2>


- Log back into the windows-vm
- Back in Wireshark, start a packet capture up
- Filter for SSH traffic only
- From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
- Open PowerShell, and type: ssh labuser@<private IP address>
    - Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark
    - Exit the SSH connection by typing ‘exit’ and pressing [Enter]

<h2>(Observe DHCP Traffic)</h2>
- Back in Wireshark, filter for DHCP traffic only
- From your Windows 10 VM, attempt to issue your VM a new IP address from the command line
     - Open PowerShell as admin and run: ipconfig /renew
     - Observe the DHCP traffic appearing in WireShark



<h2>Observe DNS Traffic)</h2>
- Back in Wireshark, filter for DNS traffic only
- From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are
    - Observe the DNS traffic being show in WireShark




<h2>(Observe RDP Traffic)</h2>
Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)
Observe the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted





<h2>Lab Cleanup (DON’T FORGET THIS)<h2/>
Close your Remote Desktop connection
Delete the Resource Group(s) created at the beginning of this lab
Verify Resource Group Deletion
