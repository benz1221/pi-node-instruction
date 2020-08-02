Navodila za namestitev

Win 10 home, pro .... + WSL2 + Docker namizje
1. korak
Najprej posodobite win do različice 2004 [win 10 version 2004]"(https://support.microsoft.com/en-us/help/4028685/windows-10-get-the-update)"
2. korak
Odprite powershell kot administrator - nato vnesete prvi ukaz (samo kopiraj prilepi) - dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
3. korak
drugi ukaz - dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
4. korak
ponovni zagon računalnika 
5. korak
ročno prenesite in namestite [namestitev wsl2 link](https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel#download-the-linux-kernel-update-package)
6. korak
Odprite powersheel kot skrbnik - zadnji ukaz - wsl --set-default-version 2
ko je vse končano, 
7. korak
namestite docker [docker desktop link](https://www.docker.com/products/docker-desktop) 

S spoštovanjem Ekipa SLovenije (bamisonic in prevod coco195).


