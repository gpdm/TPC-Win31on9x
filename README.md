# TPC-Win31on9x

Microsoft included the capability to run Windows 3.1 on top of Chicago (Windows 95's development name
during Beta days).
They said about it themselves:

```
Chicago can run Windows 3.1 on a separate screen, if you wish.
```

Well, let's do that!

This project is meant to document this lost capability, which never made it to the Windows 95 final release,
and provide a means to install it to Windows 95, yet even Windows 98 (and, somewhat, Windows Me), to try it out yourself.


# What is it?

Microsoft speaks about running Windows 3.1 in a VM, technically speaking a [Virtual DOS machine](https://en.wikipedia.org/wiki/Virtual_DOS_machine#DOS-based_VDMs).

This is achieved bascially by four files:

 * `win31.exe`, a custom loader application (similar to `win.com`), specifically to make Windows 3.1 run on Windows 95
 * `win31.pif`, a PIF file for said loader
 * `dualmous.drv`, a mouse driver tailored to run conflict-free within the VDM
 * `dualcomm.drv`, a serial driver tailored to run conflict-free within the VDM


# Which releases are available?

Microsoft included this capability in Chicago builds 81 to 328.

This repository includes just the version from build 116 and build 328, although they differ not too much from each other.

The main difference is the "switch-back" icon, that is used to return to Chicago/Windows 95.
Build 116 refers to "return to Chicago", while build 328 refers to "Return to Windows 95".
Accordingly, the icons have been changed.


# System Requirements

 * Windows 95 RTM, or Windows 98/SE RTM
 * Windows Me RTM is also possible, but the mouse is not working
 * Windows 3.1 or 3.11 must be installed to your hard drive side-by-side to Win9x
  * Windows for Workgroups 3.1/3.11 is also fine
  * Windows 3.0 is not supported


# Installing Windows 3.1/3.11

Unless you have Windows 3.1x already installed, you can still install it from within Windows 9x,
but you must exit to MS-DOS mode.

* run `lock c:`
* run `setup.exe` from the Windows 3.1x install media
 * chose to install Windows 3.1x to a new directory
 * when asked, deny Windows 3.1x to change `CONFIG.SYS` and `AUTOEXEC.BAT`, you won't need any changes to these files at all!
* once done, `exit` from MS-DOS back to Windows 9x


Windows Me doesn't have MS-DOS mode any more.
But you can restore that using this [community patch](https://github.com/gpdm/TPC-WinMe-DOSMODE).
Once done, follow the procedure outlined above.


# Installing this Distribution

An INF installer is provided for your conven












# Excerpt from original Windows Chicago Beta Release Notes

The following excerpt has been taken from the Chicago Beta 1 release notes,
dated 5/31/1994.

This is how Microsoft described to use the feature back then.

## Windows 3.1 running in a VM
Chicago can run Windows 3.1 on a separate screen, if you wish. Note that the applications will have to be installed separately for Windows 3.1 and Chicago in this case. 

You should only run Windows 3.1 in VGA mode (640 x 480, 16 color).  The reason for this is that many Windows 3.1 video drivers require the presence of a separate Windows 3.1 VDD.  The VGA driver does not have this requirement and so it functions correctly on the Chicago VDD.  The ability to run on other drivers depends on their requirements.  It may or may not succeed.

To run Windows 3.1 under Chicago
1. Copy the file WIN31.EXE from your \CHICAGO\SYSTEM directory to your Windows 3.1 directory (usually C:\WINDOWS).
2. Edit the following lines in the file SYSTEM.INI in your Windows 3.1 directory (usually C:\WINDOWS\SYSTEM.INI):

Change	To

```
COMM.DRV=COMM.DRV	COMM.DRV=C:\CHICAGO\SYSTEM\DUALCOMM.DRV
MOUSE.DRV=MOUSE.DRV	MOUSE.DRV=C:\CHICAGO\SYSTEM\DUALMOUS.DRV
```

Do this only if the original lines accessed the COMM.DRV and MOUSE.DRV files (the right side of the "=" sign).
3. Set the Command Line and Working Directory in the WIN31.PIF file to reference your Windows 3.1 directory, if it is something other than C:\WINDOWS. To access these properties:
	a. Right click on the file C:\CHICAGO\SYSTEM\WIN31.PIF
	b. Choose Properties from the context menu
	c. Choose the Program Property Sheet
	d. Make sure that the Command Line entry starts with your Windows 3.1 directory. Make sure that the Working Directory entry is your Windows 3.1 directory.  
4. In your Chicago Main group, create a link to the file  \CHICAGO\SYSTEM\WIN31.PIF.

To access Windows 3.1, double-click the icon you just created. Please do not perform Control Panel-related operations from Windows 3.1. However, you can run any application from the Windows 3.1 screen and it will run in a Windows 3.1 environment. To return to Chicago, click on the Chicago icon that will be visible on your Windows 3.1 screen.


# Acknowledgements, Copyright

This is original application binaries provided by Microsoft, and thus subject to their Copyright,
(c) 1981,1994 Microsoft Corp.

Strictly speaking, it's not allowed to redistribute these files.
The motivation lies in documenting an interesting technological feature,
making it available to the retro community and tech enthousiats, for the sole
purpose of showcasing historical software capability and it's behaviour.

