# Installing and Configuring Windows 11 Machine on virtual manager
## Overview 
---
>[!info]
>This Writeup contains the information on how to install and configure a windows 11 machine on the virtual machine manager
>

## Configuration of Virtmanager 
---
>[!NOTE]
>Go to Edit → preferences and **Enable XML Editing**


## Step 1 : Installation of the .iso file 
---
1. Head over to the [Microsoft Website](https://www.microsoft.com/en-us/software-download/windows11) and download the Windows 11 iso file for the system 

>[!note]
>The windows 11 machine supports only the 64 bit CPU and is not compatible with any 32 bit architecture


2. Once you have downloaded the .iso file , Open the Virtual machine manager **Go to "File → New Virtual Machine"**
![](images/Pasted%20image%2020251213085846.png)

3. Select the local installation media and hit forward, Then choose the iso file that you have downloaded from the website.
![](images/Pasted%20image%2020251213090103.png)

4. Configure the CPU and Cores accordingly , I have chosen the following specifications **4096 RAM and 4 cores CPU**
![](images/Pasted%20image%2020251213090258.png)

5. Now to configure the storage , By clicking on manage
![](images/Pasted%20image%2020251213090856.png)
6. Since I have already already configured my external HDD in the following [setup]([Debian-13 KVM and Qemu setup](Debian-13%20KVM%20and%20Qemu%20setup.md)) . I will proceed to create a new volume , By clicking the `➕` Symbol next to volumes
![](images/Pasted%20image%2020251213091047.png)

7. After creating the volume select it and Then begin to configure the network settings using bridged mode
![](images/Pasted%20image%2020251213092432.png)

8. Go to **Overview → XML** and scroll down till you see HyperV
![](images/Pasted%20image%2020251213113935.png)

Replace the HyperV XML code with this
```xml
<hyperv mode="custom">  
  <relaxed state="on"/>  
  <vapic state="on"/>  
  <spinlocks state="on" retries="8191"/>  
  <vpindex state="on"/>  
  <runtime state="on"/>  
  <synic state="on"/>  
  <stimer state="on">  
    <direct state="on"/>  
  </stimer>  
  <reset state="on"/>  
  <vendor_id state="on" value="KVM Hv"/>  
  <frequencies state="on"/>  
  <reenlightenment state="on"/>  
  <tlbflush state="on"/>  
  <ipi state="on"/>  
  <evmcs state="on"/>  
</hyperv>
```

>**Note:** If you have an AMD processor, you cannot use the 'hv-evmcs' feature. This [VMCS](https://www.qemu.org/docs/master/system/i386/hyperv.html) feature is only available for Intel platforms.
>You must remove the line '<evmcs state="on"/>' from the following XML. I've highlighted it in bold.

9. After Hitting the Apply go to TPM and do the following config 
![](images/Pasted%20image%2020251213114350.png)

>[!NOTE]
>This is done because Win 11 only supports 2.0


8. Hit Begin installation 
![](images/Pasted%20image%2020251213114619.png)

## Step 2 : Installation of the VM machine 
---

1. Select the KB Input 
![](images/Pasted%20image%2020251213115002.png)
2. Click on **install windows 11 and I agree checkbox**
![](images/Pasted%20image%2020251213115020.png)
3. Click on" **I dont have product key**"
![](images/Pasted%20image%2020251213115117.png)
4. Accept the terms and conditions 
![](images/Pasted%20image%2020251213115308.png)

5. Click on Next and Begin installation 
![](images/Pasted%20image%2020251213115401.png)

6. You will get this screen 
![](images/Pasted%20image%2020251213115452.png)

