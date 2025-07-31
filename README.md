<h1>Active Directory: Configuring Domain Controller and Adding Client Computer to Network</h1>


<h2>Description</h2>
I completed my first Active Directory Project and it was a really cool experience. Going through this lab allowed me to gain a better understanding of how Active Directory works behind the scenes and the different configurations that are available. For example: Managing users and permissions as well as configuring DHCP to automatically assign a range of IP addresses to the network. This hands-on experience has allowed me to feel more confident about  what exactly Active Directory is and why it is important.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Virtual Box</b>
- <b>PowerShell</b> 

<h2>Environments Used </h2>

- <b>Windows 2019 Server</b>
- <b>Windows 10 Pro</b>




<h2>Project walk-through:</h2>

<p>
I built a virtual home lab environment using Windows Server 2019 and a Windows 10 Virtual Machine . This was done with VirtualBox using a Windows Server 2019 ISO and a Windows 10 ISO. The Windows Server will serve as the domain controller and will be configured with two network adapters: NAT and an Internal network. The NAT will be used to allow my private IP to be mapped to a public IP for connectivity to the internet. The internal network will be for the Windows 10 client computer. The internal network will be configured with DHCP to allow the client computer to receive an IP after joining the domain. DHCP is a protocol that can be configured to assign a range of IP addresses to a network so they can be automatically leased for a period of time when a computer joins the domain.

After getting the server up and running, the first thing I did was configure the IP address and DNS address for the internal network adapter in the network settings. This configuration will allow the client computer to receive an IP address through DHCP once it joins the internal network. This connectivity will be allowed through the installation of Remote Access and NAT on the server.


 <img width="859" height="581" alt="image" src="https://github.com/user-attachments/assets/c25ac4b6-b41c-4a39-b5b4-ca11e79d359b" />

Now that the IP and DNS addresses have been configured, the next thing I did was install Remote Access and NAT so that the windows 10 client computer can be on an internal network but still be able to access the internet through the domain controller with DHCP.

 <img width="856" height="523" alt="image" src="https://github.com/user-attachments/assets/6aadb7a2-eb60-43f6-a9da-4558f4ca0b50" />

 
I installed DHCP and created a scope with a range of IP addresses so an IP can be provided to the client computer when it joins the network. It was in this step that I learned that you could configure a range of IP addresses to be automatically assigned to client computers as well as set the amount of time that IP can be used before it expires which is also known as the IP’s lease. Now that DHCP is installed and the scope is created, I am now able to configure the DHCP options for this particular scope. This is where I can add an IP address for a router that will be used by client computers, and I am using the same IP address that I configured on the internal network adapter.

 <img width="913" height="636" alt="image" src="https://github.com/user-attachments/assets/c8bf4050-0a5c-4637-ae41-8bd160f125b0" />


Before configuring and adding the client computer, I wanted to make my lab more realistic by adding sample users to the domain, so I created an Admin account for myself. I also used a PowerShell script that created users within a new Organizational Unit. I don’t have a lot of experience with PowerShell so running my first PowerShell script and understanding how it works and what it does was a really cool experience. The script takes a list of names and splits each name into a first and last name based on where the space is located in the list and assigns them into variables. It then creates a username for each person by taking the first letter of the first name and the full last name to be stored in the username variable. Now that the script to create the usernames is done, the rest of the script creates the users and adds them to a new Organizational Unit called USERS. This can be seen as a form of automation and is a more efficient way to create multiple users at once.

 <img width="906" height="636" alt="image" src="https://github.com/user-attachments/assets/78c9e6c0-74e3-4ce5-8a2b-7ea876568b52" />
 <img width="905" height="431" alt="image" src="https://github.com/user-attachments/assets/4452ab09-c643-4857-8004-c3633c0d9c74" />
 <img width="903" height="638" alt="image" src="https://github.com/user-attachments/assets/82f70697-5204-429d-b94c-708d9b2bbdaf" />
 

 
 
 


Now that the server is configured with DHCP and has sample users in the domain, I can create the Windows 10 client machine and add it to the domain I created. The client will be configured with an internal network adapter so we can connect to the internal network and get an IP address from the domain controller through DHCP. 
 
 <img width="847" height="444" alt="image" src="https://github.com/user-attachments/assets/5e47f0fc-caba-460e-84c9-016ebce396b8" />
 <img width="866" height="611" alt="image" src="https://github.com/user-attachments/assets/a812b3af-b59e-467b-bf34-20769c436c34" />



Getting the client computer and users added to the domain with the proper configurations pretty much wraps up the lab and I would say that I really learned a lot about Active Directory and the purpose of managing permissions for users with different access needs. This lab allowed me to strengthen my skills in Windows networking and domain management.

</p>
