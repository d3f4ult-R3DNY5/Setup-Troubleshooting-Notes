# Using the PDQ deployment and PDQ inventory in AD
## Overview 
---
This writeup contains the information about the PDQ deploy and PDQ Inventory. 

>[!NOTE]
>#### Perquisites 
>- Signing in to the webpage that contains the [PDQ software](https://www.pdq.com/)
>- Downloading the deployment and inventory Software 
>- Creating a trial account for the PDQ softwares


>[!NOTE]
>The following task are to be performed 
>- installation of software on the client machine 
>- deleting the software on the client machine 
>- viewing the installed software on the client machine 


### Task 1 : installing Zoom on the client machine using the PDQ Deploy
----
1. Open the PDQ Deploy applications and head to the packages to view all of the packages that is  installed on the machine 

![](../images/Pasted%20image%2020260202100956.png)

2. Now we are going to create a target list which includes all of the computers on which the package will be installed , Click on `New Target List`

![](../images/Pasted%20image%2020260202101153.png)

3. We know the details on which PC Patty is logged into by using the hostname command  

![](../images/Pasted%20image%2020260202101304.png)

4. Click on `Choose Targets ---> Active Directory ---> Computers` and then select on `E-PC-02` and move it to the right pane by clicking on `>`, Hit `OK`

![](../images/Pasted%20image%2020260202101446.png)

![](../images/Pasted%20image%2020260202101603.png)

5. Head to the `package Library` and search for the `Zoom in the search bar`, Select on `Zoom Client`

![](../images/Pasted%20image%2020260202101835.png)

6. Once the package is Downloaded , head to the Packages again 

![](../images/Pasted%20image%2020260202101959.png)

7. Drag that package to the HR computers target , Where you will be greeted by the following screen , and Click on `Deploy Now` 

![](../images/Pasted%20image%2020260202102205.png)

![](../images/Pasted%20image%2020260202102419.png)

8. Now if you head to the machine `E-PC-02` you will notice that Zoom is installed on the PC

![](../images/Pasted%20image%2020260202102702.png)

9. You can also view the reports that is associated with that package by heading into the reports sections of the PDQ

![](../images/Pasted%20image%2020260202103017.png)

![](../images/Pasted%20image%2020260202103034.png)


### Task 2 : Viewing the computer connected to the domain 
---
1. Open the PDQ deployment , To view all of the computers that is in the domain , You can head over to the `Add Computers ---> Active Directory Sync`

![](../images/Pasted%20image%2020260202105251.png)

2. Then you can choose the **containers to sync**, You can click on which containers to include and exclude 
![](../images/Pasted%20image%2020260202105331.png)

>[!TIP]
>Here the containers **refer to the organizational unit or Folders**

3. Then you can click on `Sync now` button of the containers 
4. Now to view the details of the computers in the domain head to the `Domain name` in my case it is the `localserer.local` and head to the `Computers and click on the corresponding PC` Here you will get the detailed statistics of which PC

![](../images/Pasted%20image%2020260202105708.png)

>[!INFO]
>You can get the various information such as Up time , hostname, OS info, AD info, Users , hardware statistics, Files and Directories and much more information

![](../images/Pasted%20image%2020260202110038.png)

5. You can view the installed applications on the PC, and also uninstall the applications on the PC by Heading into the `Applcation` 

![](../images/Pasted%20image%2020260202110243.png)

6. You can also view the deployments by heading into the deployment tab of the PC 
![](../images/Pasted%20image%2020260202110339.png)

7. You can also create new scanners to scan for new items by heading to `New scanners` option 

![](../images/Pasted%20image%2020260202110650.png)

8. You can also head into the tools pane to use the tools on the windows PC

![](../images/Pasted%20image%2020260202110916.png)





