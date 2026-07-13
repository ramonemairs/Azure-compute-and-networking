# Azure-compute-and-networking


<img width="1166" height="832" alt="image" src="https://github.com/user-attachments/assets/0d4550d1-df2f-4f6c-bcea-2581628cbb39" />

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

Go to [](https://portal.azure.com/cobrand/?id=12&mkt=DA-DK&cbcxt=azubill) and create an accout on in the account go to the search bar and type 
Resource Group and create a new Resource Group give it a name and put it in East US 2 then click rewiew and create 



<img width="828" height="1792" alt="image" src="https://github.com/user-attachments/assets/bbb3bffe-6002-4451-9360-c15bb831287b" />
<img width="828" height="1792" alt="image" src="https://github.com/user-attachments/assets/4c0d2a66-f58e-4fda-ac2c-46b0033433a3" />



Now it time to create a virtual machine and add it to the resource group we just created, so go to the search bar and type in virtual machine or VM and click create new vm now when creating the virtual machine make sure to put the resource group to the one we previously made and for the name you can name it windows vm  put the region to East US 2 and for the operating system or image* put it to windows 10 or windows 11 and for the size try to pick something with a least two VCPUS then create your username and password ( Make sure to click the box under licensing ) then click review and create then create please make note of you Virtual network in networking because you need it to create you Linux- VM.




<img width="862" height="1452" alt="image" src="https://github.com/user-attachments/assets/c4d6028d-8016-4c5c-84d6-a6017d6ed1dc" />


Once the VM is created redo everything we just did  create a next virtual machine and name it linux-VM for the resource group please use the same resource group as the windows VM (NetworkRM) put the region to East US 2 for the operating system or image put it to Ubuntu Server 22.04 or 24.04 LTS and pick the same 2VCPUS for the size then create your username and password ( Make sure to click the box under licensing ) and click next until you get to networking go to virtual network and use the same on as your windows-VM.




<img width="2344" height="1440" alt="image" src="https://github.com/user-attachments/assets/71e6d0aa-5413-41f6-9db5-fdc2fa0976da" />


 Now  if you don't have it download remote desktop and connect it to your windows VM if you don't know how to do it look for the plus + button and click it and click add new PC now go to azure and type VM then scroll to the side and look for public IP address and copy it and paste it in remote desktop the put in your username and password  and press enter.



<img width="2878" height="1692" alt="image" src="https://github.com/user-attachments/assets/c46d36e8-419b-403f-a678-fa696f8e0232" />

install
If you are login go to browser and istall wireshark [](https://www.wireshark.org) yo

