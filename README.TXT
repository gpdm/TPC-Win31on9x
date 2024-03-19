Windows 3.1 Support for Windows 95
---

This package does include the Windows 3.1x compatibility
files, that were included with Windows 95 during it`s early development,
then still known as `Chicago`.


All files have been installed to C:\Windows\System\Win31,
with links to the support files from the original builds 116 and 328
placed on the Startmenu.


To try out the historic Windows 3.1 support feature on Windows 95
(it also works on Windows 98, and to some extend on Windows Me),
please follow the procedure outlined below.



1. Install Windows 3.1x
---

Please install Windows 3.1 or Windows 3.11 (3.0 is not supported).
This must be done from MS-DOS Mode:

1. start MS-DOS Mode
2. run `lock c:`
3. run `setup.exe` from the Windows 3.1/3.11 install media

   - don´t install to your C:\WINDOWS directory
   - select `custom install` and choose a different directory, e.g. C:\WIN31
   - when asked, deny any changes to `C:\CONFIG.SYS` and `C:\AUTOEXEC.BAT`.
     None of these changes are needed.
4. run `unlock c:`
5. `exit` from MS-DOS Mode back to Windows 95

Note: For Windows Me, a community patch is provided to re-enable MS-DOS mode.
      Please check the main README.MD on the github project page.


2. Copy the Dist files over to Windows 3.1x
---

1. From the Start Menu, choose the desired build directory, either `116` or `328`
2. Select all files, and copy them to your Windows 3.1x directory, e.g. `C:\WIN31`
3. In your Windows 3.1x directory, locate `SYSTEM.INI` and open it with Notepad
4. Look for the following lines:

     mouse.drv=mouse.drv
     comm.drv=comm.drv

   Change them to read as follows:

     mouse.drv=dualmous.drv
     comm.drv=dualcomm.drv

   Save the file and exit.
5. In your Windows 3.1x directory, locate the copied `WIN31.PIF` file.
   Open the PIF properties, and change the command line and working directory
   to reflect your Windows 3.1x path, e.g.

   PATH: C:\WIN31\WIN31.EXE
   Working Dir: C:\WIN31
6. Once done, run `WIN31.PIF` and Windows 3.1 should start in a new session

  