# ¡Willkommen im PI Network Wiki!

**Dieses Wiki enthält Anweisungen zur Installation des PI Network-Knotens**

Der Inhalt dieses Wikis ist eine gemeinsame Anstrengung der PI Network-Community, da einige Schritte für einige nützlich sein können, für andere jedoch aufgrund des Unterschieds zwischen Betriebssystemen sowie Routern und sogar nicht von Internet Service Providern. Es ist unnötig zu erwähnen, dass einige Schritte technisches Wissen erfordern.

Im nächsten Abschnitt findest du Video Anleitung für verschiedene Betriebssysteme: [Video Instruction](https://github.com/pi-node/instructions/wiki/(DE)-Video-Instruktionen). 

Im Prinzip musst du deine Node zunächst aktivieren. Wenn du die Software PI Node  auf dem Computer startest, dann liest du aus der Mobile APP einen Code aus und fügst ihn in die PI Node Anwendung auf dem PC ein. Anschließend wird die nötige Software auf deinem System installiert, dann wird der Knoten überprüft (siehe 3 orangene Punkte) und als Abschluss siehst du einen rot-orangen Schalter, mit dem du deinen Knoten ein oder ausschalten kannst. 

Auf Windows Rechnern gilt es zunächst Docker Desktop einzurichten, worauf die PI Knoten innerhalb von sogenannten Docker Containers ausgeführt werden können. In den Einstellung von Docker Desktop sollte WSL2 als Virtualisierungs System verwendet werden. Dazu Windows 10 >= Version 2004 bzw. Windows 11 erforderlich. Eventuell muss die Virtualisierung im BIOS eingeschaltet werden. 

Aktuell wurde das Video für die Installation der PI Node App auf MacOS bedauerlicherweise entfernt. Die Schritte sind mit der Windows Version vergleichbar. 

Im nächsten Schritt muss die Firewall auf dem PC geöffnet werden für die Ports 34100 bis 34109. Außerdem muss im Router die Portweiterleitung für die genannten Ports auf den verwendeten Rechner eingerichtet werden. 

Bei den Einstellungen für die MAC OS Firewall ist zu bedenken, dass die Einstellungen jeweils nur für eine bestimmte Software vorgenommen werden. In diesem Fall gibt das für die Software Docker für die die Portfreigabe vorzunehmen ist. 

Weitere textliche Detailinformationen finden sich im Chat Pioniere Deutsch -> Mods FAQ -> Was ist eine Node. 

Ist alles korrekt eingerichtet kann mit dem Port Scanner auf einer Webseite der deutschen MODS unter https://pi-mods.de/nodeports/ überprüft werden, ob der Node erreichbar ist. 