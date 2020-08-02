Navodila za namestitev

Win 10 home, pro .... + WSL2 + Docker namizje
1. korak
Najprej posodobite win do različice 2004 [windows 10 posodobitev na verzijo 2004 link](https://support.microsoft.com/en-us/help/4028685/windows-10-get-the-update)
2. korak
Odprite powershell kot administrator - nato vnesete prvi ukaz (samo kopiraj prilepi) - **dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart**
3. korak
Najprej ponovno zaženite sistem (restart) 
4. korak
drugi ukaz - **dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart**
5. korak
ponovni zagon računalnika 
7. korak
ročno prenesite in namestite [namestitev wsl2 link](https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel#download-the-linux-kernel-update-package)
8. korak
Odprite powerheel kot skrbnik - zadnji ukaz - **wsl --set-default-version 2**
ko je vse končano, 
9. korak
namestite docker [docker desktop link](https://www.docker.com/products/docker-desktop) 

S spoštovanjem Ekipa SLovenije (bamisonic in prevod coco195).


