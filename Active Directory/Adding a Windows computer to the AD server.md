# Adding a Windows 11 Computer to the Active Directory Server 

## Overview 
---
This Writeup contains the information on how to add a windows 11 Pro computer to the AD server

>[!NOTE]
>#### Prerequisites 
>- Windows 11 pro VM 
>- Windows Server 2022
>#### Preconfig
>- Server : localserver.local 
>- Accounts : HD-01, Administrator 
>- Passwords for all accounts : Password1

## Phase 1 : IP configuration and Creating the user 
---
1. Head to the Server 2022 VM  `Click on the VM Tab ---> Settings` 

![](../images/Pasted%20image%2020260126110635.png)

2. Head Over to the `Network Adapter` and Click `Custom` , In my case I have selected `VMnet8`

>[!NOTE]
>- You want the server and the Network to belong to the Same Virtual Network Segment , So that they can communicated with each other 

![](../images/Pasted%20image%2020260126112850.png)

3. Repeat the same for the Windows 11 Virtual machine 
4. Head back to the `Server VM 2022` and configure a static IP address to it. To view the currently assigned IP type in the following command 

```cmd
ipconfig
```

![](../images/Pasted%20image%2020260126112821.png)

5. Head over to the `Control Panel ---> Network and Sharing Center ---> Ethernet Properities ---> Internet Protocol Version 4 (TCP/IPv4) Properties`

![](../images/Pasted%20image%2020260126113215.png)


6. Now do the same for the Windows Machine 11 `Control Panel ---> Network and Sharing Center ---> Ethernet Properities ---> Internet Protocol Version 4 (TCP/IPv4) Properties`

![](../images/Pasted%20image%2020260126122957.png)

7. Test the reachability **from windows 11 machine to Windows server by pinging the server using the command given below**

```cmd
ping 192.168.84.3
```

![](../images/Pasted%20image%2020260126113905.png)

8. In the Windows 11 machine Head over to the optional features `Settings ---> System ---> About ---> Domain or Workgroup`, And click `Change`

![](../images/Pasted%20image%2020260126121100.png)

![](../images/Pasted%20image%2020260126123045.png)

9. Now I am going to add the helpdesk account and connect it here 
![](../images/Pasted%20image%2020260126123139.png)

10. Restart the Windows 11 Machine after joining the domain
11. Login in to the account head over to `Settings ---> System ---> Optional features`
![](../images/Pasted%20image%2020260126130151.png)

>[!TIP]
>#### Adding the following tools 
>- RSAT : DHCP Server Tools 
>- RSAT : active directory domain services and lightweight directory services tools
>- RSAT : DNS server Tools
>- RSAT : Server Manager 

12. once this is done then you can login in to the account on the domain

## Phase 2 : Creating the Organizational Units 
---
>[!NOTE]
>This phase involves the creation of the organization units to store the computers with the similar functions 

1. Head to the `Active Directory Users and Computers` and Right click on the domain `Go to New ---> Organizational Unit`
2. In my case I am going to create two organization units which are **IT and HR** Respectively, The Resultant O/P is the screen shot given below 

![](../images/Pasted%20image%2020260127093738.png)

3. Head to the `User directory ---> Right Click ---> New ---> User`, Create New User with the details as given below 
![](../images/Pasted%20image%2020260127093940.png)

>[!TIP]
>![](../images/Pasted%20image%2020260127094153.png)
>- Password : Password1

4. Once the user is created, Then move the **User Patty** from `User folder ---> HR Folder`, Similarly Move the **User helpdesk** from `User Folder ---> IT folder`
5. Once the users are moved to the respective folder, Then you could head to the Folder where the user is located and `right click on the user ---> Attribute Editor ---> View the different attributes associated with that account` 
									OR
	Alternatively you could use the `net user <uname> /domain` command 

![](../images/Pasted%20image%2020260127095245.png)

![](../images/Pasted%20image%2020260127100637.png)

6. Using another VM I created using an unattended installations , I have **joined the credentials to the domain using the user account patty** 


## Phase 3 :  Creating the password policy and Account Policy for the the Domain
---
1. Hit the `Win + R ---> Type gpmc.msc`, This will open the group policy management console 

![](../images/Pasted%20image%2020260127153803.png)

2. Head to the following `Forest.localserver.local ---> Domains ---> localserver.local ----> Default Domain Policy ---> Settings Pane `

![](../images/Pasted%20image%2020260127154013.png)

3. Now `Right Click ---> Default Domain Policy on the left hand side and click Edit`, You will be greeted by the screen in the below SS

![](../images/Pasted%20image%2020260127154507.png)

4. Head to the following path `Computer COnfigurations ---> policies ---> Windows Settings ---> Security Settings ---> Account Policies ---> Password Polcies`, I have replaced it with the settings as shown in the below screenshot

![](../images/Pasted%20image%2020260127154938.png)

5. Head to the following path `Computer Configurations ---> policies ---> Windows Settings ---> Security Settings ---> Account Policies ---> Account Lockout Polcies`, I have replaced it with the settings as shown in the below screenshot

![](../images/Pasted%20image%2020260127155157.png)