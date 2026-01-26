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

## Phase 2 : Creating a account in the active directory 
---
>[!Note]
>1. creating a normal user account 
>2. creating a help desk account 

1. Head to the `ACTIVE DIRECTORY USERS AND COMPUTERS`

![](../images/Pasted%20image%2020260126100006.png)

2. If you ca click on the `view tab -> Advanced features` Then you will be able to see the epth configuration that is associated with the account

>[!TIP]
>- Includes the groups that the user belongs to 
>- Include where the user is located 

3. Head over to the computer folder and `Right Click ---> Find`, You will get a popup like this 

![](../images/Pasted%20image%2020260126100401.png)

4. Now go to the `In` options and **instead of computers replace it with the Entire Directory options**

>[!NOTE]
>This will find for any of the user and the computer in the entire directory 

![](../images/Pasted%20image%2020260126100552.png)

5. Now Double click on the `Guest User` and what will open up is the Guest Properties 

>[!TIP]
>#### Member of Tab 
>This will show all the groups that the guest is a member of 
>![](../images/Pasted%20image%2020260126100814.png)
>#### Object Tab 
>This will show where exactly the object is located 
>![](../images/Pasted%20image%2020260126100851.png)


6.  Now we go on to create the **Admin account for the user Helpdesk**, Head over the `User Folder` and `Right Click on the Administartor User ---> Copy`

![](../images/Pasted%20image%2020260126101119.png)

7. Enter the details in my case 

>[!TIP]
>- First name : `helpdesk`
>- User logon name : `HD-01`
>- Password : `Password1`

## Phase 3 : Enabling the Recycle bin 
---
>[!NOTE]
>The recycle bin must be enabled incase of **any accidental deletion**


1. Head over to the `Active Directory Administrative Center` and Head to the `domain name(local)` , On the Right hand pane `Click on Enable Recycle Bin` and Agree to the Dialogue Box

![](../images/Pasted%20image%2020260126101922.png)

2. Once the Recycle Bin has been enabled the option would be greyed out 

![](../images/Pasted%20image%2020260126102020.png)