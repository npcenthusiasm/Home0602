# 樹莓派軟硬體基本設定

## 1.上網下載映像檔(官方作業系統)
   https://www.raspberrypi.org/downloads/raspbian/  
   選擇 Raspbian Stretch with desktop Download ZIP


## 2.下載Etcher 
   https://www.raspberrypi.org/documentation/installation/installing-images/README.md  
   Download Etcher and install it.
    
    
## 3.燒錄作業系統
   選擇樹莓派映象檔，燒錄作業系統至SD卡
   燒錄完後將SD卡退出來並重插一次(若有跳出格式化的視窗，請不要格式化)
   
***
    
在燒錄好的映像檔 boot 磁區中建立2個檔案  使用NotePad++  編輯器下方Windows(CR LF)改成Unix(LF)格式

1. 建立一個"空檔案" 檔名叫ssh(小寫)並且沒有副檔名
   作用:一個開關，把樹梅派的ssh打開

2. 建立一個wpa_supplicant.conf

       ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
       update_config=1
       country=TW
       
       network={
       ssid="ErciNet"
       psk="00000000"
       }

筆電要連手機熱點

有線網路連樹梅派 控制台\網路和網際網路\網路連線\  選擇 無線網路連線>內容>共用 打勾 允許其他網路使用者透過這台電的網際網路連線來連線

cmd輸入 ipconfig 找無線網路
無線區域網路介面卡 Wi-Fi:
IPv4 位址 . . . . . . . . . . . . : 192.168.137.128

用angry ip 192.168.137.0  到 192.168.137.255
   
正常會搜尋到2個 1個是raspberry 1個是自己   
*** 
### 1.使用Putty 
輸入 raspberry ip 

    login as: pi
    Psd:raspberry
    
輸入進到設定

    sudo raspi-config
1. Change User Password
2. Network Options 
   * N1更改Hostname
   * N2設定Wi-fi
3. Boot Options
   * B3 Splash Screen 關閉 disable
4. Localisation Options
   * I1 Change Local 更改語系....只有改選項變中文而已
   * I2 Change Timezone 設定時區>Asia Taipei
5. Interfacing Options
   * P1-P5 全部 啟用 enable 
7. Advamced Options
   * A1 Expand Filesystem Ensures...

然後重開機
存檔2次  

    sudo sync
    sudo sync
重開機  

    sudo shutdown -r now
或

    sudo reboot
關機  

    sudo shutdown -h now


    
     
        
    
    
    
