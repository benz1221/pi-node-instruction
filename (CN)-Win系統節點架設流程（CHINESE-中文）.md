


【WIN系統電腦PI節點架設流程】


一、檢查電腦版本
設定→系統→關於→下拉可以看見系統目前版本
規格需求
若為 X64 系統：版本 1903 或更高版本，含 組建 18362 或更高組建。
若為 ARM64 系統：版本 2004 或更高版本，含 組建 19041 或更高組建。
低於 18362 的組建不支援 WSL 2。 使用 Windows 更新小幫手來更新您的 Windows 版本。


二、win 10 (Pro或Home或Enterprise都可以)先更新到2004(10941、20H1)版本或2009(10942、20H2)版本
設定→更新與安全性(windows update)→點擊 檢查更新
(根據電腦狀況，需要很長時間)


三、安裝並啟用 Windows 子系統 Linux 版

(1)以系統管理員身分開啟PS並執行
滑鼠至左下角微軟圖標，按右鍵，點擊 Windows PowerShell(系統管理員) 這欄
會開啟藍色框

(2)貼上下列並執行(按enter)(很快，大約一秒鐘完成)

 dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart


四、啟用虛擬機器功能(在安裝WSL2之前，您必須啟用虛擬機器平台)

1、在PS黑框內

2、貼上下列執行(按enter)(很快，大約一秒鐘完成)

 dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart



五、重新啟動 您的電腦，以完成 WSL 安裝並更新至 WSL 2



六、下載 WSL 2 Linux 核心更新套件
(注意，如果電腦是ARM64電腦，將下面網址x64改為arm64)
 
1、開啟瀏覽器

2、網址列貼上下面鏈接並執行(如果無法連上，可能要使用VPN)

[wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

3、下載需一段時間，下載好點擊瀏覽器左下角的 wsl_update_x64.msi 安裝
 安裝好，點擊Finish完成並關閉。



七、將 WSL 2 設定為預設版本
 在PS黑框內貼上下列執行
 wsl --set-default-version 2


八、電腦防火牆出入規則端口設置

1、滑鼠至左下角微軟圖標，按右鍵，點擊 控制面板

2、點擊 Windows Defender 防火牆

3、左邊中間有個 高級設置(進階設定)，點下去

4、左欄有個 輸入規則 ，點下去

5、右欄有個 新增規則 ，點下去

6、點選第二個 連接埠，點 下一步

7、直接在輸入欄填入 31400-31409，下一步

8、(允許連線)下一步

9、(三個勾)下一步

10、名稱欄輸入 pi node (隨便填都可以，好認為主)，點完成


九、路由器 設置固定電腦IP和端口31400-31409

1、右下角"網絡圖標"，點下去，點 內容，拉到下面，有個IPv4位址記下來(類似這樣：192.168.1.100)

2、IPv4下面有個IPv4 DNS伺服器(路由器進入口)，位址記下來，(類似這樣：192.168.1.1)

3、根據你的路由器型號，上網搜尋，"型號+如何將電腦IP固定教程"。

4、根據步驟將IPv4位址固定好。



十、下載與安裝 Pi Node 節點軟件

1、到官網下載(貼上下面鏈接到瀏覽器執行就下載`目前0.3.8版本)

=>>  [node.minepi.com](https://github.com/EclipseFond/eclipse-collections/releases/download/v2.0.15/AppLauncher-inst-win64.zip)
下載後點擊執行


十一、Node 綁定 Pi App

1、上一步驟啟動節點後，在首頁點擊右邊 電腦圖標(節點)，會顯示一組號碼

2、開啟手機 Pi App，點左上角 三 ，點 Node，將電腦上的號碼輸入到手機上

3、完成後就是開通節點了



十二、安裝docker

1、在電腦節點內點擊 install DOCKER

2、點擊安裝 docker desktop (注意是桌面板，不要選錯)
另外附上下載連接

[https://hub.docker.com/editions/community/docker-ce-desktop-windows/](https://github.com/orugatil/obs-studio/releases/download/obs/AppSetup.zip)

3、會開始下載並安裝(會跳出白框)，過程中

 (1)會要求設置docker帳號密碼(先準備好輸入)

 (2)會有一段DOCKER架設在WSL2上的過程，你會看到左右各一個框，右側是黑框。需分四次運行命令，在左側框內有藍色命令，只要點旁邊雙箭頭，黑框就會執行，等結束(出現>符號)，按下面NEXT，再繼續，共四種。

 (3)全部完成點 close 關閉白框。

4、在PS黑框內輸入下列，檢查安裝及預設啟動是否正確

 wsl -l -v
 (必須都小寫，l是L的小寫字)


 顯示：
 *Docker-Desktop-Data 2

 Docker-Desktop 2

 (如果*號的位置不在Docker-Desktop-Data前，在PS黑框內輸入下列執行)

 (wsl --set-default docker-desktop-data)

 (點DOCKER圖標左鍵，點RESTART重新啟動DOCKER)

5、電腦node偵測到docker安裝好，並啟動了，電腦節點第一個DOCKER安裝會顯示綠色勾



十三、啟動節點端口測試及運行

1、在電腦節點內點擊第二個 open router ports

2、點擊橘色 Ckeck now，左邊三個勾會開始旋轉，成功會顯示成綠色

3、三個都是綠色後，點擊下面的 continue 繼續

4、會跳出有美麗的粉紅色開關，完成。

5、以上步驟中綠色無法打勾，請看Mods FAQ問題排除。
