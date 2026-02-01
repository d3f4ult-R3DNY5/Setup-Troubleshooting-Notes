### Task 2 Connecting the windows remote registry 
---
>[!NOTE] 
>As you know that windows Remote Desktop involves disconnecting the user , What if we can view and see the changes through the windows registry without disconnecting the user 
>

1. Head to the registry settings using `Win + R ---> regedit.exe ---> File ---> Connect the network registry ---> `

![](../../images/Pasted%20image%2020260201122048.png)

2. Search for the PC `E-PC-02` , In most cases you will get this error ![](../../images/Pasted%20image%2020260201122228.png)

>[!NOTE]
>Since we know that the PC is connected to the network and we are able to ping it , So the only Plausible solution is that the **PC Remote registry service is not running** 

3. If we head to Patty's PC we can see that the Remote Registry Services is disabled , So you can click to properties to enable it **NOTE do this while being Admin**
![](../../images/Pasted%20image%2020260201122520.png)

![](../../images/Pasted%20image%2020260201122736.png)

4. Now if you head to the machine containing helpdesk 

![](../../images/Pasted%20image%2020260201151106.png)

