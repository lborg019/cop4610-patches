- Course [Syllabus](https://users.cs.fiu.edu/~fortega/fall16/cop4610/syllabus.html)

- [Download](https://www.virtualbox.org/wiki/VirtualBox) and install VirtualBox for your Operating System

- [Download](https://users.cs.fiu.edu/~fortega/storage/cop4610/cop4610.vdi) the image and save it in a sensible. (Creating a folder for it usually works well).

## Loading the image in VirtualBox:
1. (After installation); open the VirtualBox application.
2. Click `New`
3. Type a sensible name (e.g.:"COP4610", "Operating Systems", "OS", "Covfefe")
4. Select `Linux` from the Type dropdown options
5. Select `Ubuntu` for version (64 or 32 bits according to your computer/laptop architecture)
6. Memory size depends on your machine. `1024` is a good rule of thumb; `2048` if you have memory to spare.
7. Check the `Use an existing virtual hard disk file` option. Click on the folder button to the right. Find the `.vdi` image you downloaded and click `Open`.
8. You should now have something like this:

![image](media/snap1.png)

Just select the image, and click `Start` to launch.

**Possible error for Windows 10 users:**

(Skip this step if no issues were encountered)

Upon clicking `start`, some users might get an error dialog box with the following message:

`VT-x is not available (VERR_VMX_NO_VMX).`

There are three common reasons for this error:

- Your CPU doesn't support VT-x or AMD-V virtualization
- VT-x or AMD-V is not enabled in BIOS (UEFI)
- You have Hyper-V virtualization enabled in Windows.

Follow this [link](http://druss.co/2015/06/fix-vt-x-is-not-available-verr_vmx_no_vmx-in-virtualbox/) for possible fixes.

## Running the image

Upon successful launch, your image will load and you will eventually end up with this:

![snap2](./media/snap2.PNG)

- the default **user** is obviously :`cop4610-desktop`
- the default **password** is: `4610test`
- the default **HOST** key is: `right control` on Win10 and `right command` on OS X

## Warnings / Error messages

This is a very old Linux release, so upon entering the correct password and accessing the desktop, it is likely you will be prompted with multiple Error / Warning dialog boxes with unformation such as:

- Version of ubuntu not supported anymore
- Software updates are available for this computer
- Metacity is not responding

Just ignore all warnings and close all windows and you should still be able to use the system.

## Running the system on fullscreen:

As you might have noticed, this Ubuntu GUI is scaled down. Attempting to run it in Fullscreen (HOST+F) or Scaled mode (HOST+C) will not fix it, so do not bother trying it!

Instead, users have to install the Guest Additions CD Image.
This feature is bundled with VirtualBox, so just go on your VirtualBox toolbar:

`Virtual Box toolbar / Devices / Insert Guest Additions CD Image`
![snap3](./media/snap3.png)

## Installing Guest additions:
Your image might not be scaling up, and putting it in scaled mode does not work either.
Install guest additions to fix that.

## Apt-get failures:
Attempting to install  packages from apt-get will fail.
i.e.

`$ sudo apt-get install git`

yields:
```
Package git is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source
E: Package git has no installation candidate
```
So you can fix is by changing your `/etc/apt/sources.list` file:


## Using snapshots

## Virtualbox Portforwarding

## Accessing image from Terminal/Putty


# Making the image run faster (more cores)

# Recompiling the systems with -j (jobs) flag to make it faster.

## Do NOT increase the video memory to 64MB
(This will crash the system on boot)

useful link
https://www.virtualbox.org/manual/ch04.html