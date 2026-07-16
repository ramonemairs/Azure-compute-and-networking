# Azure-compute-and-networking


<img width="1166" height="832" alt="image" src="https://github.com/user-attachments/assets/0d4550d1-df2f-4f6c-bcea-2581628cbb39" />
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
[
](https://www.google.com/url?sa=t&source=web&rct=j&url=https%3A%2F%2Fonedata.ai%2Fmicrosoft-azure%2F&ved=0CBYQjRxqFwoTCKCml8zxz5UDFQAAAAAdAAAAABA4&opi=89978449)


This tutorial outlines some of Microsoft Azure networking activities 

[
](https://www.google.com/url?sa=t&source=web&rct=j&url=https%3A%2F%2Fsiliconangle.com%2F2022%2F05%2F24%2Fmicrosoft-announces-new-azure-capabilities-around-cloud-native-apps-data-analytics-hybrid-cloud-operations%2F&ved=0CBYQjRxqFwoTCKCml8zxz5UDFQAAAAAdAAAAABBT&opi=89978449)[
](https://www.google.com/url?sa=t&source=web&rct=j&url=https%3A%2F%2Fsiliconangle.com%2F2022%2F05%2F24%2Fmicrosoft-announces-new-azure-capabilities-around-cloud-native-apps-data-analytics-hybrid-cloud-operations%2F&ved=0CBYQjRxqFwoTCKCml8zxz5UDFQAAAAAdAAAAABBT&opi=89978449)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- PowerShell
- Wireshark
  

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu (linux)


Azure lab Prerequisites 

- create resource groups
- create a virtual networks and subnet
- Create Azure virtual machines (windows and linux[Ubuntu])
- perform network activities between the windows and Linux servers in remote desktop
   


<img width="828" height="1792" alt="image" src="https://github.com/user-attachments/assets/996836c9-b77e-413a-9af5-7df7c31d5b3c" />

Go to [](https://portal.azure.com/cobrand/?id=12&mkt=DA-DK&cbcxt=azubill) and create an accout, on the account go to the search bar and type 
Resource Group and create a new Resource Group give it a name and put it in East US 2 then click rewiew and create 



<img width="828" height="1792" alt="image" src="https://github.com/user-attachments/assets/bbb3bffe-6002-4451-9360-c15bb831287b" />
<img width="828" height="1792" alt="image" src="https://github.com/user-attachments/assets/4c0d2a66-f58e-4fda-ac2c-46b0033433a3" />



Now it time to create a virtual machine and add it to the resource group we just created, so go to the search bar and type in virtual machine or VM and click create new vm now when creating the virtual machine make sure to put the resource group to the one we previously made and for the name you can name it windows-vm  put the region to East US 2 and for the operating system or image* put it to windows 10 or windows 11 and for the size try to pick something with a least two(2) VCPUS then create your username and password ( Make sure to click the box under licensing ) then click review and create then create please make note of you Virtual network in networking because you need it to create you Linux- VM.




<img width="862" height="1452" alt="image" src="https://github.com/user-attachments/assets/c4d6028d-8016-4c5c-84d6-a6017d6ed1dc" />


Once the VM is created redo everything we just did  create a next virtual machine and name it linux-VM for the resource group please use the same resource group as the windows VM (NetworkRM) put the region to East US 2 for the operating system or image put it to Ubuntu Server 22.04 or 24.04 LTS and pick the same 2VCPUS for the size then create your username and password ( Make sure to click the box under licensing ) and click next until you get to networking go to virtual network and use the same one as your windows-VM.




<img width="2344" height="1440" alt="image" src="https://github.com/user-attachments/assets/71e6d0aa-5413-41f6-9db5-fdc2fa0976da" />


 Now  if you don't have it download remote desktop and connect it to your windows VM if you don't know how to do it look for the plus + button and click it and click add new PC now go to azure and type VM then scroll to the side and look for public IP address and copy it and paste it in remote desktop then put in your username and password  and press enter.



<img width="2878" height="1692" alt="image" src="https://github.com/user-attachments/assets/c46d36e8-419b-403f-a678-fa696f8e0232" />


 Once inside go to browser and  download  wireshark [](https://www.wireshark.org) you can get the Windows x64 installer version , once wireshark is downloaded click next to everything and install.



<img width="1988" height="1324" alt="image" src="https://github.com/user-attachments/assets/5befa40a-57e5-4401-baf3-d389c9aecbf4" />


once in wireshark feel free to observe it .



<img width="1952" height="1324" alt="image" src="https://github.com/user-attachments/assets/85ed8905-1235-4972-952c-578ea9b22238" />


Now in Wireshark click  Ethernet and once it is highlighted click the blue shark fin on the upper left. if done right it should look like a bunch of letters and numbers being made they are IP packets ( which means a chunk of data sent over the internet that contains information) , now its time to filter for ICMP traffic only to do that go to the search bar and type (ssh).



<img width="828" height="1792" alt="image" src="https://github.com/user-attachments/assets/1f149ee6-4280-4452-b9ee-272cee411245" />


<img width="2876" height="1708" alt="image" src="https://github.com/user-attachments/assets/59aec125-be9d-4d37-9a0f-b620f3a00ea8" />




Now its time to Retrieve the private IP address of the Ubuntu VM (linux-vm) and attempt to ping it from within the Windows 10 VM, so first go to azure and type in VM in the search bar double click the linux-vm we created and scroll down and look for the private IP address mine is          ( 172.16.0.5 ) copy it and go back into the window-VM or remote desktop and go to the start button and open powershell, so from the  Windows-vm   i will attempt to ping the linux-vm ip address , so first go to powershell and type ( ping then click the space bar and then paste the linux IP address then click enter) we should see the ICMP traffic in wireshark if you can't  paste the ip address just type it out.



<img width="2880" height="1650" alt="image" src="https://github.com/user-attachments/assets/11faada3-7d4e-4b8e-a169-eea5bb2f8b95" />


Now where going to Configuring a Firewall [Network Security Group], so first back in powershell where going to initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM so go to  powershell and  type ( ping then click the space bar and then paste the linux IP address then space bar again then -t ) and now you should see a nonstop ping. 



<img width="2810" height="1050" alt="image" src="https://github.com/user-attachments/assets/5d6c2459-fc87-40c5-a7bc-fb90121ecc09" />


<img width="828" height="1792" alt="image" src="https://github.com/user-attachments/assets/00d36ed5-2bac-43e5-9b5e-aec43543ba8a" />


Now where going to open the Network Security Group which your Ubuntu-VM is using and disable incoming (inbound) ICMP traffic,so go to the  Azure portal and search for VM  and open your Linux-vm go to networking epand it by clicking the arrow next to it and go to network settings once in look to the right  where network security group is click the highlighted word under it which would be ( linux-vm-nsg ) once in go to settings expand  it and click inbound security rules and now lets add a new rule so click the add (+) button  and now lets create the rule.for 
( source ) put any 
( source port ranges ) put * 
( service ) put custom 
(Destination port ranges ) put * 
( protocol ) ICMPv4
(Priority ) 290 
then click add. 



<img width="2870" height="1684" alt="image" src="https://github.com/user-attachments/assets/750ea71d-bc79-4bef-9f19-7ac4a145fdad" />


Go back to Windows-VM in remote desktop go to powershell and observe the ping requests being timed out PLEASE NOTE: it mate time sometime before you see the rule being implemented.



<img width="2880" height="1694" alt="image" src="https://github.com/user-attachments/assets/19a18da1-26d4-4ea3-87b4-116cf0903c72" />



Now lets Re-enable ICMP traffic for the Network Security Group your Ubuntu-VM is using first back into you linux-vm  go to networking epand it by clicking the arrow next to it and go to network settings once in look to the right  where network security group is click the highlighted word under it which would be ( linux-vm-nsg ) once in go to settings expand  it and click inbound security rules and just delete the rule we just created ( the ICMP deny rule ) once it is deleted go back to remote desktop and observe the ICMP traffic is running again PLEASE NOTE: it mate time sometime before you see the rule being implemented.




<img width="2880" height="1718" alt="image" src="https://github.com/user-attachments/assets/54574084-a7f2-4fc5-886f-ff3dfda2a274" />

Now its time to observe SSH (secure shell)  traffic so back in wireshark where you filter for ICMP go ahead and filter for SSH if PLEASE NOTE: if wireshark is not working just close remote desktop and log back in. so now from your Windows-VM SSH into  your Ubuntu Virtual Machine ( from its private IP address) so first open azure and search VM and go to your linux-vm and double click it and scroll down and look for you private IP address and copy it, after open remote desktop and go to powershell to find powershell click the start or windows  button at the bottom left of the screen and type powershell and open it now type in ssh ( labuser@<private IP address> ) so mine is ( ssh space shammie@172.16.0.5 ) then click enter, now observe the ssh traffic in wireshark. 




<img width="2874" height="1668" alt="image" src="https://github.com/user-attachments/assets/48a21df9-8a17-4162-b6ae-c668c9e36c97" />


Now after clicking enter powershell will ask if you want to continue connecting (yes/no/[fingerprint])? just type yes and click  enter now its time to type your linux password PLEASE NOTE: when typing in your password nothing will appear,this is for security purposes just type in the correct password and hit enter. if done correctly your prompt should change mine is now (shammie@linux-vm) now take something to observe it you can type things like ( id,hostname,uname space bar  -a,) to see ssh traffic in wireshark. Now you can exit the SSH connection by typing (exit) and pressing enter.


That's  the end of the lab that's  just a few networking activities  that can be done with Microsoft Azure.



