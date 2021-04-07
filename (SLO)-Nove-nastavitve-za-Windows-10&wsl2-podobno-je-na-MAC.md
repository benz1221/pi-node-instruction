**# (SLO) Nove nastavitve za Windows 2004 wsl2**

## Navodila za namestitev

Win 10 home, pro …. + WSL2 + Docker namizje

Upoštevajte korak za korakom in ne hitite – – NO Ubuntu, kali, debian AWS, VPS,.. NE dovolite si klonirati aplikacij ali programov ker boste obžalovali…..

PREDEN ZAČNETE s samo  namestitvijo nastavite domače omrežje na zasebno in NE javno, saj potem samo potrdite vse med samo namestitvijo….
slike imate objavljene tudi na naši neuradni strani [nastavitev noda](https://www.pinetwork.si/ios/)

1. korak Najprej posodobite win do različice 2004 [20H2, nekateri imate opcijo 21H1]([Posodobitev windowsov](https://support.microsoft.com/en-us/help/4028685/windows-10-get-the-update))” Po končani posodobitvi sistema, če niste sledili navodilom spodaj odstranite svoj docker v kolikor ste ga najprej naložili iz računalnika ali toolbox ali desktop, ne pozabite pripadadajočih pod-datotek tudi izbrisati (mi smo uporabili program REVO Uninstaller kateri poišče tudi podmape). Brezplačna različica NE počisti vsega!! Nato pojdite na korak 2.

2. korak Odprite powershell kot administrator – nato vnesete prvi ukaz (samo kopiraj prilepi oranžni text) – dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

Windows uporabniki imate cmd!! (ukazni poziv) in PowerShell uporabite Powershell 

Mac uporabniki imate terminal!!

3. korak drugi ukaz – dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

4. korak ponovni zagon računalnika

5. korak ročno prenesite in namestite namestitev wsl2 link za 64 bitne sisteme 

namestite si ⇓
[namestitev wsl2 link za 64 bitne sisteme ](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

6. korak Odprite powersheel kot skrbnik – zadnji ukaz – wsl –set-default-version 2

NE nameščajte dodatnih distribucij (Ubuntu, kali …. ali drugih)

7. Sedaj namestite docker. Pazljivo izberite za kateri sistem ga boste naložili⇒ docker desktop [link](https://docs.docker.com/release-notes/)

Dobro poglejte kateri docker boste naložili na svojo mašino!!!
Windows 7,8  64 bit priporočamo toolbox (Navodila za Docker toolbox so tukaj https://drive.google.com/open?id=1dv3paeo-MhJMSe9rjGfdXvylI24Fps4r v sliki in razlagi).
Windows 10 64 home, pro, enterprise, ultimate docker desktop
Mac book docker desktop

8. NAMESTITE DOCKER na vaš sistem.

Preverite, da imate virtualizacijo omogočeno, v nasprotnem primeru ne boste mogli naložiti dockerja!! Težave pri virtualizaciji najdete na tem naslovu ⇒ [Hyper -V](https://techcommunity.microsoft.com/t5/itops-talk-blog/step-by-step-enabling-hyper-v-for-use-on-windows-10/ba-p/267945) .

PUSTITE PRIVZETE NASTAVITVE, NE SPREMINJAJTE NIČESAR…. SKIP TUTORIAL !!!

9. OPEN PI NODE APP check ports in boste dobili kontejner.

Postopek namestitve Pi Noda©

Pojdite na uradno stran node.minepi.com ter si namestite pi node na računalnik!!

Po uspešni namestitvi boste prejeli kodo katero morate vnesti v pi app (v vašo napravo- telefon).

Kodo vpišite v  pi app (telefon).⇒ Odprite pi v telefonu pojdite v profil, ter vstopite v node. Tu sedaj prepišite kodo iz pi noda (na računalniku) v pi app ⇒ (node) ter potrdite. Sedaj ste sinhronizirali vašo napravo z vašim telefonom. Sedaj lahko operirate ali s pi nodom ali pi app kar preko računalnika. Vendar podaljševanje cikla je možen samo s telefonom !!

V samem dockerju v razdelku settings preverite, da imate wsl2 obkljukano.

Ni veliko razlike, med sistemi mac ali win, na katerem poganjamo NODE. Uporabniki imajo največ težav, ker so nepravilno nastavili statični ipv4 in port forwarding v usmerjevalniku, najlažje je, da pogledate na internetu navodila za vaš model usmerjevalnika (nekateri usmerjevalniki imajo možnost dodajati vsako izjemo vrat poebej npr. 31400-31400, 31401-31401,..imeti morate vnešena vrata od 31400-31409). V pomoč vam je tudi vsebina na povezavi [modem in ruter nastavitev](https://www.pinetwork.si/modem-in-ruter-nastavitve/)

Za uporabnike MACa kako dodajati izjeme v požarni zid sledite navodilu spodaj.

1.Iz Apple  menija, izberite System Preferences.

2. Izberite Security & Privacy.

3. V razdelku Security & Privacy izberite zavihek Firewall in kliknite Firewall Options.

Opomba: Če je ta možnost siva, kliknite ikono ključavnice v spodnjem levem kotu pogovornega okna, da odklenete to možnost za spremembe.

4. Naslednje pogovorno okno omogoča dodajanje ali odstranjevanje programov s seznama požarnega zidu in konfiguriranje, kako požarni zid obravnava zahteve iz teh programov. Če želite dodati program, kliknite znak + na dnu seznama.

5. Izberite želeno aplikacijo, ki bo dovoljena skozi požarni zid.

6. Preverite, ali je program nastavljen na Allow incoming connections.

Same nastavitve vašega noda lahko testirate tudi sami.

Kliknite na ⇒ [port test](https://www.ipfingerprints.com/portscan.php) za test vaših vrat “portov”.

Odprite docker ter izberite images. Tu morata biti samo 2 sliki v kolikor ste pravilno pridobili concensus 

Preverite katere kontejnerje imate:
win – cmd
docker ps -a
in
wsl -l -v
pogledate. če imate instaliran wsl2 kernel pravilno
Mac uporabniki uporabit terminal in vnesite ukazno vrstico
docker ps -a

Odprite vaš brskalnik in vnesite localhost:31401(to boste dobili samo če imate concensus). V kolikor imate kje 0 niste uspešno nastavili noda (izpustili ste korak ali celo niste uspešno pobrisali pod datotek dockerja,…). V kolikor ne veste zakaj imate 0 nas prosim kontaktirajte preko maila pinetworkslo@gmail.com

V kolikor imate stellar dummy uporabite v brskalniku text localhost:31400 in dobili boste odziv OK v kolikor ga ne dobite ste prav tako nekje zgrešili vnos v usmerjevalniku.

Uporabite⇒ [Pi Testnet dashboard](http://dashboard.pi-blockchain.net/), če dobite zeleno vrstico. V kolikor je rdeča imate težavo in jo bo potrebno odpraviti.

Uspešne transakcije vaše denarnice (samo za imetnike pi noda in kreirane denarnice!!) si lahko pogledate na povezavi [TU](https://pi-blockchain.net/ledgers)!! Veselo raziskovanje vam želimo.

S spoštovanjem Ekipa Slovenije.

(bamisonic in coco195).
