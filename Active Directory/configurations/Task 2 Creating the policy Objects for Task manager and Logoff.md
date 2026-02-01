### Task 2 Creating the policy Objects for Task manager and Logoff
---
1. In the `gpmc.msc`, head to the `Groip Policy Objects Folder` and Right Click and Name the Policy 

![](../../images/Pasted%20image%2020260201164141.png)

2. In this case i Have create the Policy for the task manager and Right click on it and hit `Edit`

![](../../images/Pasted%20image%2020260201164403.png)

![](../../images/Pasted%20image%2020260201164441.png)

3. Since Task Manager Comes under the `User Configurations > Admin Templates > System > Ctrl + Alt + Del Options` and double click on it 

![](../../images/Pasted%20image%2020260201164900.png)

4. Click on `Enabled ---> Apply ---> OK`

![](../../images/Pasted%20image%2020260201165015.png)

5. Once done Drag the Policy over to the `HR OU` and will get Prompted as the screenshot Given below and Hit OK 

![](../../images/Pasted%20image%2020260201165251.png)

6. Now head over to the `HR OU Right Click on the Task manager Policy and Click Enforced`

![](../../images/Pasted%20image%2020260201165413.png)

7. Now go to the cmd and run this command on the E-PC-02

```cmd
gpupdate /force
```

![](../../images/Pasted%20image%2020260201165805.png)

#### Similarly creating the policies for Logoff 

![](../../images/Pasted%20image%2020260201170132.png)

![](../../images/Pasted%20image%2020260201170205.png)

8. Results 

![](../../images/Pasted%20image%2020260201170350.png)

