# Merhaba Pidaşlar.
Bu bölümde öncelikle Node ile ilgili kısa bir bilgilendirme, ardından kurulum adımları ile ilgili yönlendirmeler yapacağız. 

***


## Node Nedir
Node herhangi bir blokzincirin omurgasıdır. **Kriptoparalarda işlemlerin kaydı sistemdeki üyeler tarafından tutularak merkeziyetsiz hale gelir**. Buna **distributed ledger** yani **dağıtımlı kayıt defteri** denir. Siz herhangi bir bankacılık işlemi yaparken nasıl banka bunların bir kaydını tutuyorsa (Ahmet Mehmet'e 50 TL gönderdi, Ahmet'in hesabından 50 Tl düşüldü, Mehmet'in hesabına 50 TL eklendi gibi) kriptoparalarda bunu topluluk üyeleri yapıyor. 

Bu defterleri işlemenin de farklı yöntemleri var. Bir deftere işlem kaydetmek için üyeler bu işlemler üzerinde anlaşmalıdır. Bunlar da **mutabakat algoritmaları** ile sağlanır. **Pi Stellar'ın mutabakat algoritmasını kullanır.**

Nodelar, yani düğümler, bu mutabakat algoritmasını çalıştırmak ve sonucunda çıkan işlemleri izlemek onaylamak ve blokzincire kaydetmek üzere çalışan sistem üyeleridir. Ağın işlerliğini ve güvenliğini sağlarlar.

***


## Pi Node kurulumu
[Pi Node Windows 0.4.4 -güncel-](https://node-cdn.minepi.com/Pi%20Network%20Setup%200.4.4.exe) | 
[Pi Node Mac 0.4.4 -güncel-](https://node-cdn.minepi.com/Pi%20Network-0.4.4.dmg) 
linklerini kullanarak Pi Network uygulamasını bilgisayarınıza indirin. 
Pc uygulamasından aldığınız 8 haneli kodu cep telefonunuzda Pi uygulumasının "Menu > Node" ekranındaki kutuya girip uygulamaları senkronize edin ve ardından pc uygulaması üzerinde node bölümüne gidin. 

![Pi Network Pc node](https://i.ibb.co/DCfvRqC/photo-2020-05-11-19-24-28.jpg)
![Pi Network Pc node](https://i.ibb.co/PZdhCkm/photo-2020-05-11-19-13-17.jpg)

***

## Docker Kurulumu
Mac için
--> [Docker Desktop for Mac](https://download.docker.com/mac/stable/Docker.dmg)

Windows 10 Pro ve Enterprise sürümleri için
--> [Docker Desktop for Windows](https://github.com/docker/toolbox/releases/download/v19.03.1/DockerToolbox-19.03.1.exe)

Windows 10 Home - 8.1 - 8 - 7 sürümleri için
--> [Docker Toolbox](https://github.com/docker/toolbox/releases/download/v19.03.1/DockerToolbox-19.03.1.exe)
linklerini kullanarak uygulamayı indirin.

Takip eden görsel anlatımlar Windows 10 Home versiyonu için geçerlidir.
▒▒▒
DOCKER DESKTOP ARTIK WINDOWS 10 HOME DESTEĞİ DE SUNUYOR
[BURAYA TIKLAYARAK](https://desktop.docker.com/win/stable/amd64/Docker%20Desktop%20Installer.exe) İNDİREBİLİRSİNİZ.
▒▒▒
![Docker start](https://i.ibb.co/9sdnq8V/docker1.jpg)

Masaüstünde Docker Quickstart Terminali çalıştırın.
Bunu yaptığınızda Pi uygulaması Docker'ı ardından Docker ise Virtual Manager'ı tetikleyecek ve Vm üzerinde 2.6 Default'u çalıştıracaktır. 

Kontrol etmek için docker terminal üzerinde veya cmd üzerinde 

`docker ps -a` 

komutunu çalıştırarak STATUS kısmına bakın. Burada UP yazması gerekiyor.

![Docker ps -a](https://i.ibb.co/WyFKT0t/docker2.jpg)

***
## Port Açma
### 1- Portları Windows Güvenlik duvarına ekleme:
Uygulamanın kullanacağı portları windows güvenlik duvarında aktif duruma getirmek için büyüteçe tıklayın ve arama kısmına cmd yazın. Komut istemini yönetici olarak çalıştırın ve şu komutları girin:

`netsh advfirewall firewall add rule name="Pinode wf" dir=in action=allow protocol=TCP localport=31400-31409`

`netsh advfirewall firewall add rule name="Pinode wf" dir=out action=allow protocol=TCP localport=31400-31409`

İki komut için de OK sonucu almanız gerekiyor. 

Bu işlemi manuel olarak yapmak veya kontrol etmek için **win+r** tuş kombinasyonunu kullanarak çağırdığınız **çalıştır** iletişim kutusuna **wf.msc** yazıp entera basın. Windows Güvenlik Duvarı'na gidin. 
Gelen kurallar - Giden kurallar kısmında bu girilen kuralları kontrol edebilir, sağ taraftaki "Yeni kural ekle" ile TCP bağlantı için 31400-31409 portlarını kullanan yeni bir kural ekleyebilirsiniz.

![wfmsc](https://i.ibb.co/QCZw2My/wfmsc.jpg)

### 2- Portları Router'a ekleme:

Port açmak için en doğru yönergeleri Youtube üzerinde kullandığınız modemin marka ve modeliyle birlikte gireceğiniz port açma veya port yönlendirme sorguları verecektir. Görsel anlatım TTnet Statik ip ile Tp-Link td854w_1 modem için geçerlidir.

Öncelikle 192.168.1.1 veya varsayılan ağ geçidi adresinize giderek modem arayüzüne ulaşmanız gerekiyor. 
Modem arayüzüne ulaştıktan sonra Port Yönlendirme kısmına 

Protokol: TCP 

Ip: LAN IP adresiniz (cmd'de ipconfig yazın - wireless kısmında ipv4 adresiniz)

Port kısmına: 31400:31409 yazarak gerekli yönlendirmeleri yapmanız gerekiyor. 

Alttaki örnekte bu ayar `Gelişmiş - NAT - Sanal Sunucu` bölümündedir.

![Router](https://i.ibb.co/tPDCSgC/port1.jpg)


***

## ÇÖZÜM ÖNERİLERİ:

### 1-) Modem arayüzünüzde ayrıca firewall ayarı varsa WAN adresinizden LAN adresinize yönlendirme yapmanız gerekebilir.

![Router2](https://i.ibb.co/mhrXWSV/port2.jpg)

### 2-) Docker IP almıyor veya Pi Node üzerinde hala portları göremiyorsanız Virtual Box'a manuel olarak port eklemeniz gerekebilir.

![VMPort](https://i.ibb.co/vZkqC4n/vmport.jpg)

### 3a-) Kitematic Alpha üzerinden Ayrıcalıklı Mod'u aktifleştirmeyi deneyebilir

### 3b-) Kitematic üzerinde powershell ile çalıştırmayı deneyebilirsiniz. 

![Kitematic](https://i.ibb.co/Hzm91T2/vmport.jpg)


***


Farklı işletim sistemleri - modem arayüzleri - uygulama versiyonları için bu verileri geliştirebilirsiniz.
## Pi Türkiye