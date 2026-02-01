# Common active directory tickets, CMD commands, Security Groups and the drives

## Overview 
---
This writeup contains the information about the common helpdesk tickets that are related to the accounts within the environment. 

This Writeup contains the following 

>[!NOTE]
>- Common active directory account issues 
>- CMD commands 
>- PC disable enabled
>- Account disabled , password reset, Password change on the next logon, Password expiry 
>- Security Groups , Map Drives, personal drives and Map Letter 

## 1 : Checking the connectivity to the domain 
---
1. You can check the connectivity to the domain using the ping command

![](images/Pasted%20image%2020260128094948.png)

2. You can alternatively view the IP address of the server  using the following command `nslookup <servername>`

![](images/Pasted%20image%2020260128095035.png)

3. You can check the hostname of the server using the hostname command , and alternatively ping the hostname from the user account patty 

## 2 : Account Related issues
---

>[!NOTE]
>In this will create various troubleshooting scenarios for the user account named patty which are as follows 
>- Viewing the account polices 
>- Account Password 
>- Resetting the Password / Expired Password 
>- Changing the Password on the next logon 

### Viewing the account related policies 

1. To view the account related polices we will use the following command `gpresult`  and to save the account information in an HTML file we will use the command given below 

```cmd
gpresult /H C:\Users\HR01-Patty\Documents\GPR_Patty.html
```

![](images/Pasted%20image%2020260128100302.png)

2. To update any of the policy changes we will use the command `gpupdate` to viwem more details on the command we will use the following command `gpupdate /?`


### Disabling the account 

1. To disable the account head to the `ADUC` **on the server machine** 
2. Right click on the `localserver.local ---> find` as shown below 

![](images/Pasted%20image%2020260128100915.png)

3. Search for the user Patty and `Go To Properties ---> Object` , To see where the account is located 

![](images/Pasted%20image%2020260128101640.png)

![](images/Pasted%20image%2020260128101817.png)

4. Go to where the folder is located, `Right click on thhe user Patty ---> Disable Account`
![](images/Pasted%20image%2020260128102301.png)

5. Once I restart the Guest machine, you will be greeted by this screen 

![](images/Pasted%20image%2020260128103549.png)


6. To enable the account back again you can head to the `ADUC` and `rightclick on the user ---> Enable the account`

![](images/Pasted%20image%2020260128103748.png)

7. So if you return back to the machine , you will see that patty is able to login back again

### Incorrect password entered to many times 

1. According to the password policy that is set in [here]([Adding a Windows computer to the AD server](Active%20Directory/Adding%20a%20Windows%20computer%20to%20the%20AD%20server.md)) . It takes 3 incorrect attempts 

![](images/Pasted%20image%2020260128104357.png)

2. Head to the ADUC and Find for the user patty in the domain and `click on the properties and head to the account pane` and click on the `Unlock account option`

![](images/Pasted%20image%2020260128104614.png)

3. Once again the login screen becomes available for the user patty 

### user changes the password on the next login 

1. Head to the ADUC and Find for the user patty in the domain and `click on the properties and head to the account pane` and click on the `User changes the password on next Logon`

2. You will be greeted by this screen 
![](images/Pasted%20image%2020260128105124.png)

### resetting the Password from the ADUC

1.  Head to the ADUC and Find for the user patty in the domain and `Right click on the user Patty ---> reset the password`

![](images/Pasted%20image%2020260128105623.png)

2. Patty can be able to login in with the new password that is created after the recheck 


## 3: Disabling the Desktop
---
1. Head to the `ADUC and Find for the E-PC-02` by changing the search parameters into the computers 

![](images/Pasted%20image%2020260201083931.png)


2. `Go to the Object tab and see which directory it is a member of`

![](images/Pasted%20image%2020260201084016.png)

3. Right` Click on it and Select the Disable Account` , It should look like the Screenshot given below 

![](images/Pasted%20image%2020260201084150.png)

4. Head to the Windows 11 machine and restart it for the changes to take place, Now if you notice you cant even ping the machine 

![](images/Pasted%20image%2020260201084834.png)

5. Checking if you can login in with another account on the domain 

![](images/Pasted%20image%2020260201084911.png)


6. To re-enable the account head to the same place and select enable account , Once you do that the down arrow symbol over the PC will disappear.


