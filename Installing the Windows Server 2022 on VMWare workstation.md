# Installing the Windows Server 2022 on VMWare workstation

## Overview 
---
This writeup includes the step by step installation process of the windows server 2022 on the VMWare workstations 

>[!NOTE]
>#### Specifications 
>- **VMWare Workstation Pro 17.6.4**
>- **Host Machine : Windows 11 25H2 64bit**
>- **VM : Windows Server 2022**
>- **Enabled Virtualisation in the BIOS**

## Phase 1 : Installation of the Image and Configuration of the VM
---
1. Head over to the [Microsoft Website](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022) and Download the 64bit edition
2. Then Proceed to Open the VMware workstation and click on **Create a New Virtual Machine**

![](images/Pasted%20image%2020260101142322.png)

3. Select the Typical (Recommended) installations 

![](images/Pasted%20image%2020260101142443.png)

4. Select the Installer disk image (ISO), then browse to the location where the `.iso` file is stored. Click **Next**

![](images/Pasted%20image%2020260101142942.png)

5. Enter the Default credentials, In my case it was 
	- Full Name : `Admin`
	- Password : `Password1`

![](images/Pasted%20image%2020260101143322.png)

6. Click Next, Then A popup message will appear **informing the user has not entered the windows product key**, In my case I do not have it, So I click yes 

![](images/Pasted%20image%2020260101143538.png)


7. Choose the location where you want the Virtual machine to be stored, Click next 
8. Choose How large the allotted disk space for this VM should be , I am going to choose the Default Setup in my scenario and then I select **Store Virtual Disk as a single file** 

![](images/Pasted%20image%2020260101144001.png)

9. Now I am going to select on the Customize hardware

![](images/Pasted%20image%2020260101144216.png)

10. In my installation, **I will be giving it 4GB of RAM**, Click on **Close** once you are done

![](images/Pasted%20image%2020260101144528.png)

11. Power on the Virtual machine and **If you encounter a dialogue box given in the below screenshot then proceed with the following steps below,** otherwise skip to Phase 1 : Step 

![](images/Pasted%20image%2020260101144942.png)

12. If you encountered the Dialogue Box, then Power Off the virtual machine and head to **Edit Virtual machine Settings**

![](images/Pasted%20image%2020260101145217.png)

13. Head to the floppy drive and **unselect the checkbox that says `Connect at power on`**, Hit OK

![](images/Pasted%20image%2020260101145340.png)

14. Now Power On the machine and Select **Language, Time and KB layout according to your preferences, I am leaving it default in my installation**

![](images/Pasted%20image%2020260101145559.png)

15. Click on **Next**, Hit  `Install Now`
![](images/Pasted%20image%2020260101145702.png)

16. In this installation , I am  selecting the `Windows Server 2022 (Datacenter Evaluation Desktop Experience)` 

![](images/Pasted%20image%2020260101145953.png)

17. After Selecting the Custom Installation, Select the Unallocated Drive, Click Next

![](images/Pasted%20image%2020260101150138.png)

18. Then enter the password for the Admin Account 

![](images/Pasted%20image%2020260101151339.png)

## Phase 2 : Installing the updates
---
1. When your greeted by the sceen below , Head to **VM---> Send Ctrl + Alt + Del**

![](images/Pasted%20image%2020260101151636.png)

2. Head to **"Settings ---> Windows Update"** and Install all of the Windows Update 

![](images/Pasted%20image%2020260101152056.png)

3. Once your done withe the updates create a Snapshot, So you can revert to this point if the installation or any of the configuration goes wrong 

![](images/Pasted%20image%2020260101154222.png)

