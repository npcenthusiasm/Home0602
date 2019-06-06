# 樹莓派軟硬體基本設定

### 1.上網下載映像檔(官方作業系統)
    https://www.raspberrypi.org/downloads/raspbian/
    
    選擇 Raspbian Stretch with desktop Download ZIP


### 2.下載Etcher 
    https://www.raspberrypi.org/documentation/installation/installing-images/README.md
    
    Download Etcher and install it.
    
    
### 3.燒錄作業系統
    選擇樹莓派映象檔，燒錄作業系統至SD卡

***
    燒錄完後將SD卡退出來並重插一次(若有跳出格式化的視窗，請不要格式化)
    
    使用NotePad++ 在SD卡內建立2個檔案  編輯器下方Windows(CR LF)改成Unix(LF)格式
    
    1.建立一個"空檔案" 檔名叫ssh(小寫)並且沒有副檔名   --->   一個開關 把樹梅派的ssh打開
    
    2.建立一個wpa_supplicant.conf   --->   新增熱點
    
    ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
    update_config=1
    country=TW

    network={
    ssid="ErciNet"
    psk="00000000"
    }
    
    筆電要連手機熱點
    
    有線網路連樹梅派
    
    
