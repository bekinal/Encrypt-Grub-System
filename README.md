<h1>Encrypt Grub & System</h1>

<h2>Description</h2>
Project consists of using Grub to password-protect the Debian bootloader and prevent malicious users from obtaining information about the Linux environment
<br />


<h2>Utilities Used</h2>

- <b>VirtualBox</b>
- <b>Debian Environment</b>
- <b>Terminal</b>
- <b>Grub</b>

<h2>Password-Protect the Bootlader:</h2>
A privilege escalation attack will be conducted to portray the vulnerability of the Bootloader. Then, Grub encryption functionality will be deployed to mitigate the breach, preventing further harm from happening. 
<br />
<br />
The Debian machine is started. C is pressed as soon as the splash screen appears to enter the command-line:<br/>
<img src="https://imagizer.imageshack.com/img922/2938/jCwohu.png"
<br />
<br />
The command cat /etc/shadow is executed to read the contents of the shadow file. The command was executed with high level permissions (bad):<br/>
<img src="https://imagizer.imageshack.com/img922/6126/mA2feL.png"
<br />
<br />
The command line is exited and Debian is booted normally:<br/>
<img src="https://imagizer.imageshack.com/img922/8800/4YWLIj.png"
<br />
<br />
The terminal is opened and root permissions are accessed:<br/>
<img src="https://imagizer.imageshack.com/img924/2053/Qq3Cle.png"
<br />
<br />
The grub-mkpsswd command generates a Grub password for the Bootloader:<br/>
<img src="https://imagizer.imageshack.com/img924/3764/DpEwZg.png"
<br />
<br />
The password is copied as we cannot possibly remember all of that:<br/>
<img src="https://imagizer.imageshack.com/img923/2096/Ss9rxT.png"
<br />
<br />
A file named Grub_Pass is created:<br/>
<img src="https://imagizer.imageshack.com/img922/7595/yar2tz.png"
<br />
<br />
The password is pasted into this file:<br/>
<img src="https://imagizer.imageshack.com/img922/4111/e8Lgr2.png"
<br />
<br />
A new temrinal tab is opened as the root user:<br/>
<img src="https://imagizer.imageshack.com/img922/2366/n4DTVk.png"
<br />
<br />
The 00_header file is accessed using nano:<br/>
<img src="https://imagizer.imageshack.com/img923/6924/Xv2zJc.png"
<br />
<br />
The following lines are inserted at the bottom of the file. This creates a user and a password for the Bootloader:<br/>
<img src="https://imagizer.imageshack.com/img922/623/CvIQBR.png"
<br />
<br />
The update-grub command is executed for the changes to take effect:<br/>
<img src="https://imagizer.imageshack.com/img924/8003/Wi5m5Q.png"
<br />
<br />
The machine is rebooted:<br/>
<img src="https://imagizer.imageshack.com/img922/1189/Oo8fbj.png"
<br />
<br />
This time, pressing C will bring up a credentials window instead of launching straight into the command line (good):<br/>
<img src="https://imagizer.imageshack.com/img923/9377/L1Dtc5.png"
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
