# ATTENTION!! IF YOU HAVE DOCKER DESKTOP OR TOOLBOX UNINSTALL ALL BEFORE CONTINUE WITH SET UP BELOW!!
## Win 10 home,pro .... + WSL2 + Docker desktop First update win to version 2004 

and then follow the steps 
Use first – powershell admin – command (just copy paste)

dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

Second 
 
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

RESTART PC - manually download and install   
[Updating to wsl2 ](https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel#download-the-linux-kernel-update-package)

Open powersheel – last command  
wsl --set-default-version 2

**when all is done, install the docker at the end  with regards** bamisinic and coco195

If Docker Daemon isn't running, follow these steps.

* Open "Window Security"

* Open "App & Browser control"

* Click "Exploit protection settings" at the bottom

* Switch to "Program settings" tab

* Locate "C:\WINDOWS\System32\vmcompute.exe" in the list and expand it

* Click "Edit"

* Scroll down to "Code flow guard (CFG)" and uncheck "Override system settings"

Then restart.