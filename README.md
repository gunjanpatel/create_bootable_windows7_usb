How to Create a Bootable Windows 7 or Vista USB Drive
========================

### Steps:
1. **Plug-in your Flash Drive :** First plug-in your USB stick to your USB port and copy all the content to a safe location in your hard drive.
2. **Run Command Prompt as an administrator :** For opening Command prompt
Go to start menu and type cmd in the search box . Right click on it and select run as Administrator to use it with administrator permission.
3. Using the **Diskpart** utility find the drive number of your Flash Drive. To do the same write following command in command prompt:
```
DISKPART
```
  + Running DISKPART will display the version of DISKPART you are running, name of your PC. Run the following command:
```
list disk
```
  + Your Disk Number will be listed and note it down as you'll need this in the next step. 
  + Let us assume that the USB Drive is Disk 1 but if it depends on your disk list. Try to chose best and pay your attension when you choose disk number.

-------

4. **Format the drive by executing the following commands one by one**. 
###### Make sure you replace Disk 1 with proper Disk number .
```
select disk 1
clean
create partition primary
select partition 1
active
format fs=NTFS QUICK
assign
exit
```
After finishing with above commands you should have formatted USB disk.

5. Let's make USB drive bootable using the bootsect utility wich comming with Windows 7 disk.
  + To do so, please insert Windows 7 bootable cd in to your cd drive.
  + Now, let's assume your dc drive letter to G: and USB drive letter to H: ( Rememeber this is in most of common case it can be different.)
  + Please navigate to your cd drive direct by following command
```
G:
cd boot
```
  + Use the bootsect to make the USB Drive Bootable.
```
BOOTSECT.EXE/NT60 H:
exit
```

6. **No still not complete**
Copy all files from the Windows 7/DVD to the formatted USB stick.

7. What are you waiting for? Now boot your pc with USB boot option and rock. ;)



