### Task 2 : creating and configuring the network shares 
---
1. Head to the server manager and Click `File and Storage Services ---> Shares ---> Right Click ---> New Shares`
2. Select the `SMB Share - Quick` and do the Configurations as given below 
![](../../images/Pasted%20image%2020260201101019.png)

![](../../images/Pasted%20image%2020260201101114.png)

![](../../images/Pasted%20image%2020260201101217.png)

![](../../images/Pasted%20image%2020260201101326.png)

![](../../images/Pasted%20image%2020260201101352.png)

3. Create a Similar Share with the share name `Personal`

![](../../images/Pasted%20image%2020260201101609.png)

4. Go to the `File explorer ---> This PC ---> C drive ---> Shares ---> Right Click on the HR Folder ---> Properties ---> Sharing` to view if the drive is connected and get the drive location

![](../../images/Pasted%20image%2020260201101825.png)

![](../../images/Pasted%20image%2020260201102321.png)

5. Head to the security tab And Do the Following configurations 

![](../../images/Pasted%20image%2020260201102609.png)

6. Click on `Disable Inheritance ----> Convert Inherited Permisssion into Explicit Permissions for the Object`

![](../../images/Pasted%20image%2020260201102800.png)

7. Remove the unnecessary groups and keep the following permissions 

![](../../images/Pasted%20image%2020260201102910.png)

8. Add the **User helpdesk and the security group HR** to the HR folder , Click on `Add- Select Principal`

![](../../images/Pasted%20image%2020260201103241.png)

![](../../images/Pasted%20image%2020260201103303.png)

9. Hit `Apply and OK`, Head to the `Sharing Tab ---> Share` and change the HR from `Contribute to Read/Write`

![](../../images/Pasted%20image%2020260201103504.png)

10. Do the same for the Personal folder but add the security Group Personal 
