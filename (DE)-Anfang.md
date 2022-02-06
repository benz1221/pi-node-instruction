# ¡Willkommen im PI Network Wiki!

**Dieses Wiki enthält Anweisungen zur Installation des PI Network-Knotens**

Der Inhalt dieses Wikis ist eine gemeinsame Anstrengung der PI Network-Community, da einige Schritte für einige nützlich sein können, für andere jedoch aufgrund des Unterschieds zwischen Betriebssystemen sowie Routern und sogar nicht von Internet Service Providern. Es ist unnötig zu erwähnen, dass einige Schritte technisches Wissen erfordern.

Im nächsten Abschnitt findest du Video Anleitung für verschiedene Betriebssysteme: [Video Instruction](https://github.com/pi-node/instructions/wiki/(DE)-Video-Instruktionen). 

Im Prinzip musst du deine Node zunächst aktivieren. Wenn du Node.IP auf dem Computer startest, dann liest du aus der Mobile APP einen Code aus und fügst ihn in die Node-IP Anwendung auf dem PC ein. Anschließend wird die nötige Software auf deinem System installiert, dann wird der Knoten überprüft (siehe 3 orangene Punkte) und als Abschluss siehst du einen rot-orangen Schalter, mit dem du deinen Knoten ein oder ausschalten kannst. 

Auf Windows Rechnern gilt es zunächst Docker Desktop einzurichten, worauf die PI Knoten innerhalb von sogenannten Docker Containers ausgeführt werden können. In den Einstellung von Docker Desktop sollte WSL2 als virtualisierungs System verwendet werden. Dazu ist ggf. eine aktualisierung der Windows Software erforderlich. 

Im nächsten Schritt muss die Firewall auf dem PC geöffnet werden für die Ports 34100 bis 34109. Außerdem muss im Router die Portweiterleitung für die genannten Ports auf den verwendeten Rechner eingerichtet werden. 

Ist alles korrekt eingerichtet kann mit dem Port Scanner auf einer Webseite der deutschen MODS unter https://pi-mods.de/nodeports/ überprüft werden, ob der Node erreichbar ist. 