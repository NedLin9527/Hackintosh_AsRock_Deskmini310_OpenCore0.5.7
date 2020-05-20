# Hackintosh_AsRock_Deskmini310_OpenCore0.5.7
All contents in this website is for academic use only


## 前言：
Hackintosh 俗稱黑蘋果，近幾年Apple在消費者PC、NB市場上高貴的表現，
加上iPhone、iPad等產品整合性強，漸漸地開始有使用者希望能有更好效能表現的PC來使用macOS，
也就開使開發EFI引導macOS的技術，以達到在一般消費者電腦上實現使用macOS。

目前主流為Clover引導俗稱四葉草，再來就是我這次使用的OpenCore引導，
編程文件比較完善的還是以四葉草為主，但目前很多主流社群都開始轉往OC引導。

而我正在服役的**MacBook Pro 13” 2014mid**為使用的CPU為**i5-4278U 2Cores4Treads**，
CineBench的跑分大約在660，效能表現不佳，
基於在家日常使用且可以外接螢幕，就萌生自行安裝黑蘋果的計畫，畢竟Mac那尊絕不凡的售價，
讓還在負擔房貸的我吃不消啊！Cores且記憶體跟硬碟都有大空間的個人電腦。

*因爲相關操作有可能影響原生系統，非常建議如果只是感興趣的，就直接買一台MacBook Air來使用吧！

設備配置：  
|     Device     | info|  
|:----------------:|:-------------------------------:|  
|Case            |`ASRock Deskmini 310 Barebones`|  
|CPU             |`i5-9400 6cores 6Treads`       |  
|iGPU            |`UHD 630`                      |  
|RAM             |`Micron DDR4 2666 SO-DIMM 8Gx2`|  
|Storage         |`WD SN550 1TB`                 |  
|Wan             |`Broadcom 1820A`               |  
|OS              |`macOS Catalina 10.15.4`       |  
|EFI             |`OpenCore 0.5.7`               |  


BIOS設置  
＊Load UEFI Defaults  
＊Advanced  
        CPU Configuration, CPU C States Support: Enabled,CFG LOCK: Disabled  
        Onboard HD Audio: Enabled  
        USB Configuration, XHCI Hand-off: Enabled  
        Super IO Configuration, Serial Port: Disabled  
＊Security Secure Boot: Disabled  
＊CSM :Disabled  
  
  
製作過程：  
1.下載黑果小兵 10.15.4 鏡像檔  
2.使用Ether將鏡像寫入隨身碟  
3.置換EFI 將隨身碟上EFI清空，並將OC 0.5.7引導放入  
4.設定BIOS並使用隨身碟開機，安裝系統  
5.完成安裝後檢查驅動程式是否正常，沒問題後使用hackintool將隨身碟EFI引導覆蓋至硬碟  

過程發生問題就是透過Xcode 編輯config.plist 一開始沒注意都把要增加的資訊加在key的位置，導致一直無法用隨身碟引導，後來使用OpenCore Configurator 查看才發現，編輯config.plist 的方式不正確。  
  
參考網頁  
https://www.chenweikang.top/?p=613  
https://github.com/cocobear/DeskMini310_EFI  
  
  
我的Github
https://github.com/NedLin9527  
  
待辦事項  
＊研究單碟雙引導的方式  
