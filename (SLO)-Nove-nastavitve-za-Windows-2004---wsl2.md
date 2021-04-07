Navodila za namestitev
Win 10 home, pro …. + WSL2 + Docker namizje

Upoštevajte korak za korakom in ne hitite – – NO Ubuntu, kali, debian AWS, VPS,.. NE dovolite si klonirati aplikacij ali programov ker boste obžalovali…..

PREDEN ZAČNETE s samo  namestitvijo nastavite domače omrežje na zasebno in NE javno, saj potem samo potrdite vse med samo namestitvijo….

1. korak Najprej posodobite win do različice 2004 [20H2, nekateri imate opcijo 21H1] [posodobitev sistema]((https://support.microsoft.com/en-us/help/4028685/windows-10-get-the-update) Po končani posodobitvi sistema, če niste sledili navodilom spodaj odstranite svoj docker v kolikor ste ga najprej naložili iz računalnika ali toolbox ali desktop, ne pozabite pripadadajočih pod-datotek tudi izbrisati (mi smo uporabili program REVO Uninstaller kateri poišče tudi podmape). Brezplačna različica NE počisti vsega!! Nato pojdite na korak 2.

2. korak Odprite powershell kot administrator – nato vnesete prvi ukaz (samo kopiraj prilepi oranžni text) – 
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

Windows uporabniki imate cmd!! (ukazni poziv) in PowerShell uporabite Powershell kako do njega v sliki 2 podaj!!

Mac uporabniki imate terminal!!

3. korak drugi ukaz – 
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

4. korak ponovni zagon računalnika

5. korak ročno prenesite in namestite namestitev wsl2 link za 64 bitne sisteme 

[Uporabite korak 4](https://docs.microsoft.com/en-us/windows/wsl/install-win10#step-4---download-the-linux-kernel-update-package)

6. korak Odprite powersheel kot skrbnik – zadnji ukaz – 
wsl –-set-default-version 2

NE nameščajte dodatnih distribucij (Ubuntu, kali …. ali drugih)

7. Sedaj namestite docker. Pazljivo izberite za kateri sistem ga boste naložili⇒ [docker prenos](https://docs.docker.com/release-notes/)
Dobro poglejte kateri docker boste naložili na svojo mašino!!!
Windows 7,8  64 bit priporočamo toolbox (Navodila za Docker toolbox so tukaj [nastavitve toolbox navodila](https://drive.google.com/open?id=1dv3paeo-MhJMSe9rjGfdXvylI24Fps4r) v sliki in razlagi).

Windows 10 64 home, pro, enterprise, ultimate docker desktop
Mac book docker desktop

8. NAMESTITE DOCKER na vaš sistem.

Preverite, da imate virtualizacijo omogočeno, v nasprotnem primeru ne boste mogli naložiti dockerja!! Težave pri virtualizaciji najdete na tem naslovu ⇒ [Hyper -v](https://techcommunity.microsoft.com/t5/itops-talk-blog/step-by-step-enabling-hyper-v-for-use-on-windows-10/ba-p/267945) .

PUSTITE PRIVZETE NASTAVITVE, NE SPREMINJAJTE NIČESAR…. SKIP TUTORIAL !!!

9. OPEN PI NODE APP check ports in boste dobili kontejner.