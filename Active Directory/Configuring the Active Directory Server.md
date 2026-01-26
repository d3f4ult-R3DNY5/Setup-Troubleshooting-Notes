# Configuring the Active Directory Server

## Overview 
---
This Writeup contains the information about the configuration of the active directory server configured in the following write up 

>[!NOTE]
>**writeup** : [Installing the Windows Server 2022 on VMWare workstation](Installing%20the%20Windows%20Server%202022%20on%20VMWare%20workstation.md)

Given down below is the technical specification of the Windows server 

>[!NOTE]
>#### Technical Specifications 
>- **Host Machine :** Windows 11 25H2
>- **Virtual Machine :** Windows Server 2022
>- **Update Last performed :** 01/01/2026

## Phase 1 : Adding the AD Services and the Domain name 
---
1. Once the machine is powered on you head "**Server manger ---> Manage ---> Add Roles and Features**"

![](../images/Pasted%20image%2020260102085239.png)

2. Click **Next** till you reach the Server Selections

![](../images/Pasted%20image%2020260102085336.png)

![](../images/Pasted%20image%2020260102085849.png)

3. Once you reach the server selections, Select your server in my case the server name from my pool is **Server-2022**
4. Click on **Active Directory Domain Services** in the server Roles

![](../images/Pasted%20image%2020260102090319.png)

5. Click Next Till you reach the confirmation screen 

![](../images/Pasted%20image%2020260102090503.png)

6. Hit Install, Once the Installation is Complete Hit Close 

![](../images/Pasted%20image%2020260102090547.png)

![](../images/Pasted%20image%2020260102090931.png)

7. Click on the Flag icon and you will get a dialogue box as given below, Then click on "**Promote this server to a domain controller**"

![](../images/Pasted%20image%2020260102091555.png)

8. In my Installation, I do not have an existing domain so, I will click on "**Add a new forest**" and add a name for the root domain name, Proceed to Click "**next**"
- name : `localserver.local`

![](../images/Pasted%20image%2020260102091841.png)

9. Once , you are greeted with the Domain controller options screen then I will leave the Forest Functional Level and the Domain Functional Level the default, As for the DSRM password

>[!NOTE]
>#### DSRM 
>This is a unique administrator password that is used to access a Windows Domain Controller in a special or safe mode for r**epairing, Maintaining and restoring AD** when it is in the offline mode  

![](../images/Pasted%20image%2020260102092421.png)

10. Leave the below as it is and click next 

![](../images/Pasted%20image%2020260102092529.png)

11. You will get the NetBIOS Domain name and then Click Next

![](../images/Pasted%20image%2020260102092631.png)


12. Then you will get the Below screen which shows the location of where the database, log files and SYSVOL folder will be stored 

![](../images/Pasted%20image%2020260102092808.png)

13. Click Next To head towards the Review options 

![](../images/Pasted%20image%2020260102092922.png)

14. Install all the perquisites required for the ADDS features 

![](../images/Pasted%20image%2020260102093100.png)

15. Once the Installation is complete you will be signed out of the system
16. Then login in the system again by sending the Ctrl+Alt+Del command 

