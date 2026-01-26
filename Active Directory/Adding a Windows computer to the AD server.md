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

## Phase 1 : IP configuration and Adapter card Configurations 
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

