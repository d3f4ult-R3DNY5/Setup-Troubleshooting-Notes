# Debian-13 KVM and Qemu setup

## Overview
---
>[!info]
>This guide explains how to install, configure, and troubleshoot KVM/QEMU on Linux. And using an external drive as a storage pool for the VM storage


## 1. Prerequisites
---
- Linux Version : Debian GNU/Linux 13 (trixie)
- CPU with virtualisation enabled : Intel VT-x or AMD-v 
- Administrative privileges : **sudo access**

**Verifying the virtualisation support on the Linux system**
To verify if the system has virualizzation we enter the command which is given below 
```bash
lscpu | grep "Virtualization"
```

Since my system is an Intel based system and already has virtualisation enabled , So upon running the above command I got the following output 

![](images/Screenshot%20From%202025-10-20%2008-10-45.png)

In case if your not seeing this you will have to enable it in the BIOS/UEFI settings 


## 2. Installing KVM-QEMU  for the systems 
---
First we have to make sure that the system is upto date so we run the following command

```bash
sudo apt update && apt upgrade -y
```

In my case all the packages are up-to-date as we can see below screenshot

![](images/Screenshot%20From%202025-10-20%2008-28-52.png)

Then we proceed to install the [qemu-kvm](https://packages.debian.org/bookworm/qemu-kvm) which is a virtual package

>[!note] Virtual Package
>A virtual package is a placeholder that represents a function or feature provided by one or more real packages.

The command to install the virtual package is given as follows 

```bash
sudo apt install qemu-kvm
```

Now we need libvir package which is a virtualisation API and is needed for KVM

```bash
sudo apt install libvirt-daemon-system libvirt-clients bridge-utils
```

Add your user to necessary groups:

```bash
sudo adduser $USER libvirt
sudo adduser $USER kvm
```

Log out and back in for the group changes to take effect. This step is crucial for enabling non-privileged access to VM management functionalities.

Check the status of the libvirt service:
```bash
sudo systemctl status libvirtd
```

If it’s not running, start and enable it at boot with:
```bash
sudo systemctl start libvirtd
sudo systemctl enable libvirtd
```

Verify installation:
```bash
virsh list --all
```

This is the output we get on running the command 
![](images/Screenshot%20From%202025-10-20%2008-42-16.png)

Confirm user group membership:
```bash
groups
```

In my case the user is `t3ch`
So this is the output that I have got
![](images/Screenshot%20From%202025-10-20%2008-43-56.png)


So then we proceed to install virt-manager 
```bash
sudo apt install virt-manager
```

After this we can open this virt manager from the apps menu 


## 3. Setting up the external drive 
---
In my case I am using the following drive 
- seagate one touch HDD : 2 TB 
- SATA drive 

Before moving on to setting up the storage pool we need to do the following 

```bash
sudo nano /etc/libvirt/qemu.conf
```

Uncomment the user and the group and replace it with the username that is added to the libvirt and kvm groups , This is what should the reultant O/P be 
![](images/Screenshot%20From%202025-10-20%2008-59-01.png)


Then restart the service 
```bash
sudo systemctl restart libvirtd
```

Now open Virtual machine manager and do the following 
> File -> New Virtual Machine

![](images/Screenshot%20From%202025-10-20%2009-03-08.png)

Now sect the ISO image , Since I had already installed an ISO on my local disk i hit select local disk and click forward 
![](images/Screenshot%20From%202025-10-20%2009-17-02.png)


Browsing to the ISO media and click forward 
![](images/Screenshot%20From%202025-10-20%2009-18-00.png)

Configuring the memory and CPU settings
![](images/Screenshot%20From%202025-10-20%2009-18-47.png)

Now creating the storage space on external HDD
![](images/Screenshot%20From%202025-10-20%2009-19-42%201.png)

Click on "Select or create custom storage" and click manage
![](images/Screenshot%20From%202025-10-20%2009-21-30.png)

Click on the  `+`  icon located at the bottom left corner 
![](images/Screenshot%20From%202025-10-20%2009-22-49.png)


Now Browse to your desired storage location and give a name for the storage path and hit finish 

Now navigate to Your created pool directory in my case it is "pool"
![](images/Screenshot%20From%202025-10-20%2009-24-23.png)

And hit on the `+` Icon next to volumes 
![](images/Screenshot%20From%202025-10-20%2009-26-12%202.png)


Now click on "Choose Volume" and click Forward

![](images/Screenshot%20From%202025-10-20%2009-31-03.png)

![](images/Screenshot%20From%202025-10-20%2009-33-04.png)

Now Hit Finish


## Conclusion 
---
The KVM and QEMU setup on Debian 13 is now complete.  
You have:

- Verified hardware virtualization support (Intel VT-x / AMD-V).
- Installed and configured `qemu-kvm`, `libvirt`, and `virt-manager`.
- Added your user to the correct groups for non-root VM management.
- Enabled and verified the `libvirtd` service.
- Configured an external drive as a storage pool for VM images.

You can now create, run, and manage virtual machines directly through **Virtual Machine Manager** or the `virsh` CLI.  
This setup provides a stable, isolated, and efficient virtualization environment suitable for testing, development, or running additional operating systems.





