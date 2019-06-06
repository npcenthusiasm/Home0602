# openCV
## Lab0529
## 安裝  
切換 Tag 到4.1.0

    wget https://github.com/opencv/opencv_contrib/archive/4.1.0.zip     
    wget https://github.com/opencv/opencv/archive/4.1.0.zip

解壓縮    

    unzip 4.1.0.zip
    unzip 4.1.0.zip.1 

### 1. 安裝相關套件

* 編譯套件

      sudo apt-get install build-essential cmake
       
* 圖片套件

      sudo apt-get install libjpeg-dev libpng-dev libtiff-dev
* 影片套件

      sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
      sudo apt-get install libxvidcore-dev libx264-dev
       
* GTK套件

      sudo apt-get install libgtk-3-dev libcanberra-gtk*
       
* 最佳化套件

      sudo apt-get install libatlas-base-dev gfortran
       
* 樹莓派加裝

      sudo apt-get install at-spi2-core  

### 2. Python設定

* 安裝python3開發套件

      sudo apt-get install python3-dev
             
* 安裝 numpy 套件

      sudo pip install numpy

### 3. 設定編譯條件

* 建立編譯目錄

      cd opencv-4.1.0
      mkdir build
      cd build
       
* 修改 swapfile size

      sudo vi /etc/dphys-swapfile
      修改 CONF_SWAPSIZE=2048
      改完後
      sudo /etc/init.d/dphys-swapfile stop
      sudo /etc/init.d/dphys-swapfile start
       
### 4. 執行 cmake

    cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv/opencv_contrib-4.1.0/modules \
    -D ENABLE_NEON=ON \
    -D ENABLE_VFPV3=ON \
    -D BUILD_TESTS=OFF \
    -D OPENCV_ENABLE_NONFREE=ON \
    -D INSTALL_PYTHON_EXAMPLES=OFF \
    -D BUILD_EXAMPLES=OFF \
    -D PYTHON_EXECUTABLE=/usr/bin/python3 \
    ..
       
### 5. 編譯

* 在 build 目錄下執行

      make -j4
       
 * 編譯完成後執行

       sudo make install
       sudo ldconfig
       將 swap size 改回 100   
              
### 6. 測試

 * 執行 python
 
       python
       import cv2
沒有錯誤訊息表示成功
       
### 6. 備分資料

 * 壓縮
 
       tar zcvf opencv.tgz opencv
       
 * 解壓縮
 
       tar zxvf opencv.tgz



       
  
       
    
