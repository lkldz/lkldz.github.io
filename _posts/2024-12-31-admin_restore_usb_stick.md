---
title: Restore Pendrive.
date: 2024-12-30 10:10:00 +100
categories: [Admin, USB]
tags: [USB]
---

# <span style="color:olive">How to restore a pendrive to its default state.</span> 
---

### <span style="color:orange">Entry point</span> 

My pendrive was not visible in the *"Devices and drives"* section of Windows.
![localImage](/assets/images/admin/usb/1.jpg)

I decided to open ***Disk Management*** to check if the pendrive is detected by this program. <br> It turned out that pendrive is visible.

![localImage](/assets/images/admin/usb/2.jpg)

*For your information, I forgot that I used this pendrive to install Fedora41 on the one of my machines.* <br> 

BTW: <br> _**Anaconda**_ is an OS installer used by some of the Linux distributions.

So below, you can find the steps I took to fix my pendrive.

---
## <span style="color:orange">Steps to fix</span>

#### <span style="color:olive">1. Use command line tool: **diskpart**</span>

![localImage](/assets/images/admin/usb/3.PNG)

**<ins>diskpart</ins>** - is used to manage disks, partitions, volumes and virtual hard disks

#### <span style="color:olive">2. List available disk(s) and select USB</span>
```console
list disk
select disk DISK_ID
```
![localImage](/assets/images/admin/usb/4.jpg)

#### <span style="color:olive">3. Show information about the selected disk</span>
```console
detail disk
```
![localImage](/assets/images/admin/usb/5.jpg)

#### <span style="color:olive">4. Clean/format disk</span>
```console
clean
```
![localImage](/assets/images/admin/usb/6.jpg)

#### <span style="color:olive">5. Create new partition</span>
```console
create partition primary
```
![localImage](/assets/images/admin/usb/7.jpg)

After the partition has been created, the focus automatically shifts to the new partition

#### <span style="color:olive">6. Format disk</span>
```console
format fs=fat32 quick
```
![localImage](/assets/images/admin/usb/8.jpg)

### <span style="color:orange">Output</span>

 ![localImage](/assets/images/admin/usb/9.jpg)

 ![localImage](/assets/images/admin/usb/10.jpg)