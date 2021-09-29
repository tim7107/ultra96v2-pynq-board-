# ultra96 v2 pynq user guide
### ==Board Introduction==
* <font color="#f00">**Tutorial**</font>
    - Ultra96 官方
    >1. http://zedboard.org/product/ultra96-and-pynq-framework
    - SD card 燒錄
    >1. https://www.96boards.org/documentation/consumer/ultra96/ultra96-v2/installation/sd-etcher-install.md.html
    - Xilinx 官方
    >1. https://www.xilinx.com/
### ==啟動與基本設定==
* <font color="#f00">**Tutorial**</font>
    - 開機,基本Setting相關:
    >1. https://ultra96-pynq.readthedocs.io/en/latest/getting_started.html
    >2. https://www.youtube.com/watch?v=is34FBOlDJE&t=177s
    >3. http://www.pynq.io/?_ga=2.177882661.1441341331.1613630347-949178109.1587945572
    - Custom overlay相關:
    >1.  https://www.youtube.com/watch?v=Dupyek4NUoI&t=14s
    - 國外論壇 (因為中文教學很少,走頭無路可以上論壇發問)
    >1. https://discuss.pynq.io/
    >2. https://forums.xilinx.com/
---
- <font color="#f00">**啟動**</font>
    >1. 連接電源線,成功之後會亮綠燈
    >2. 插入燒錄好的sd card(os映像檔)
    >3. 按下SW4開關啟動板子
    >4. 用usb線 連接 板子與host(PC)，成功的話PC的檔案總管會顯示出來，如下圖
    ![](https://i.imgur.com/wYQGYHn.png)
    >5. 等一下下,打開chorme 在網址輸入 http://192.168.3.1,密碼xilinx
    ![](https://i.imgur.com/lBuDY3o.png)
    >6. 成功即可連線到jupyter
    ![](https://i.imgur.com/6xCOtUH.png)

---
- <font color="#f00">**WIFI連線(需要下載github的repo、python package才需要)**</font>
    >1. Open common->wifi.ipynb
    ![](https://i.imgur.com/cLXx2Ep.png)
    >2. 執行each shell
    ![](https://i.imgur.com/nWxHuM9.png)
    >3. In[2]輸入wifi 名稱+密碼
    >4. In[3]測試wifi是否連接成功(照片是成功的)
---
- <font color="#f00">**關機**</font>
    >1. jupyter notebook new 一個 terminal 
    ![](https://i.imgur.com/znDvmQK.png)
    >2. $sudo shutdown -P now
    ![](https://i.imgur.com/ezWt8pl.png)
    >3. 等到板子只剩下電源綠燈還亮著,就可以拔電源線了
---

### ==Overlay相關==
* <font color="#f00">**Tutorial**</font>
    - Download Vivado HLS and Vivado
    >1. https://www.xilinx.com/support/download.html
- <font color="#f00">**使用open source overlay or download project on github**</font>
    EX. https://github.com/Xilinx/PYNQ-ComputerVision
    >1. jupyter notebook new 一個 terminal 
    ![](https://i.imgur.com/znDvmQK.png)
    >2. 照著github上的教學輸入download 指令
    ![](https://i.imgur.com/0oazF8S.png)
    >3. 成功之後,jupyter就會出現新的file,裡面即可使用它的overlay
    ![](https://i.imgur.com/8fiZR8p.png)
---
- <font color="#f00">**自己寫custom overlay**</font>
    * 基本上overlay 分成2種，一種是deep learning-based的overlay,另外一種是 非deep learning-based的overlay.
    * 用deep learning 的話需要用Vitis AI 套件開發，非deep learning based 的話需要用Vivado、Vivado HLS開發。
    * 參照 https://github.com/tim7107/Hardware-acceleration-on-FPGA-Ultra96-V2-/blob/main/README.md  

### ==OS操作相關==
- <font color="#f00">**移動檔案(PC->Board 或 Board->PC)**</font>
    >0. 應該網路還有其他方法,但我紀錄我比較常用的
    >1. 當ultra96成功連線到PC後,在PC打開檔案管理員
    >![](https://i.imgur.com/vaNxmuN.png)
    >2. 紅色地方輸入 \\\192.168.3.1\xilinx  
    >3. 需要輸入帳號密碼,都是xilinx
    >4. 進去之後即可看到它的file 頁面,可以直接從PC拉檔案進去board上
    >![](https://i.imgur.com/yeZBzU5.png)
    >5. 有可能遇到permission的問題,ie權限不足
    >> <SOL> 
    >> 
    >> (i) 最一開始應該還是可以拖曳資料夾到主要目錄,但可能更裡面的file都不能移動 
    >> 
    >> (ii) 回到主要目錄,把需要的檔案(EX. overlay file)丟到主目錄
    >> 
    >> (iii) 回到jupyter, new a terminal 
    >> 
    >> (vi) 利用linux command 去移動,ie. command 加一個sudo即可
    >> ![](https://i.imgur.com/3NXise0.png)

    
