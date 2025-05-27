# activities-network-pt3


![image](https://github.com/user-attachments/assets/4ed2242a-809c-45a7-9fab-4091aef6f850)    ![image](https://github.com/user-attachments/assets/8ad90810-eb97-4e8a-877a-8c34541b3594)






<h2>(Configuring a Firewall [Network Security Group])</h2>




  
- Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM

![image](https://github.com/user-attachments/assets/1e52d039-8200-482b-9d4b-dd10a656a03d)

   
  - Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic

![image](https://github.com/user-attachments/assets/0d380db0-5275-4e8f-b5b5-05eef980f160)

![image](https://github.com/user-attachments/assets/f3355f26-b9f7-4c48-9a85-83d604208e87)



  - Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity

![image](https://github.com/user-attachments/assets/22c8188b-d56b-4760-910a-59a2f76859b4)

  - Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is


  - Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working)

![image](https://github.com/user-attachments/assets/09a49b71-7be5-441b-8074-4896fa57b73a)



  - Stop the ping activity

<h2>(Observe SSH Traffic)</h2>


- Log back into the windows-vm
- Back in Wireshark, start a packet capture up


- Filter for SSH traffic only

![image](https://github.com/user-attachments/assets/02f28c9f-d2b4-458b-9fbb-8974885f2396)

- From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)


- Open PowerShell, and type: ssh labuser@<private IP address>


    - Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark
 
  ![image](https://github.com/user-attachments/assets/b8fc99f2-4aa4-42b3-a26a-f936a05935e1)

 

    - Exit the SSH connection by typing ‘exit’ and pressing [Enter]

  ![image](https://github.com/user-attachments/assets/e308f200-1c36-470b-a5df-ec1b5fe52141)



<h2>(Observe DHCP Traffic)</h2>


- Back in Wireshark, filter for DHCP traffic only


  
- From your Windows 10 VM, attempt to issue your VM a new IP address from the command line
  
     - Open PowerShell as admin and run: ipconfig /renew

     - Observe the DHCP traffic appearing in WireShark

![image](https://github.com/user-attachments/assets/c0e1ae2e-a26b-49d9-90df-afc2ce49faac)

<h2>Observe DNS Traffic)</h2>


- Back in Wireshark, filter for DNS traffic only

  
- From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are
    - Observe the DNS traffic being show in WireShark




<h2>(Observe RDP Traffic)</h2>



- Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)

  
- Observe the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
    - Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted





<h2>Lab Cleanup (DON’T FORGET THIS)<h2/>
Close your Remote Desktop connection
Delete the Resource Group(s) created at the beginning of this lab
Verify Resource Group Deletion
