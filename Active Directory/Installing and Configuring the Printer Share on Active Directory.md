# Installing and Configuring the Printer Share on Active Directory

## Overview 
---
This Writeup contains Installations and configuration of the printers in a AD environment , In this README we will perform the following tasks 

>[!NOTE]
>- installation of the Printer services feature in the AD domain 
>- adding a printer 
>- Configuring the share permissions of the printer 

## Task 1 : Installation of printer services on the AD domain 
----
1. Go to the `server manager` on the server 2022 machine and `Manage ---> add roles and features`

![](../images/Pasted%20image%2020260202134156.png)

2. Click on Next until you reach the server roles and Select the option **Print and Document services**, Then click on `Add Features`

![](../images/Pasted%20image%2020260202134355.png)

3. Click on Next till you reach the confirmation screen , **Hit Install**
![](../images/Pasted%20image%2020260202134436.png)

## Task 2 : Adding a printer on the server 
---
>[!NOTE]
>Normally a printer would have a static IP address that associated with it and so that it doesn't create any configurations issues 

1. Go to the `Server manager` and head to the `Print Services`, Go to `Tools ---> print management`
![](../images/Pasted%20image%2020260202135054.png)

2. Go to the `Print Server ---> Server 2022 ---> printers` , Right click and `Add printer`

![](../images/Pasted%20image%2020260202135220.png)


3. You will be greeted by the following menu 
![](../images/Pasted%20image%2020260202135300.png)

>[!TIP]
>Since I don't have a printer on the network , I would select the option of **Add a new printer to the existing port**

3. you can then add the printer to the home network
4. Then Later On you can share the printer on the network and choose the printer permissions 





