# orangepi

Run Linux on Orange Pi<br>
在香橙派上运行linux

* Download orangepi version of armbian from Armbian website<br>
从Armbian下载香橙派版本的armbian<br>
https://www.armbian.com/download/<br>
![download armbian](https://github.com/Zhong-Github2020/orangepi/blob/main/armbian.JPG)


* Use SD Card Formatter remove data on SD card<br>
采用SD Card Formatter将准备好的SD card格式<br>
https://www.sdcard.org/downloads/formatter/<br>
![SD Card Formatter](https://github.com/Zhong-Github2020/orangepi/blob/main/SD_Card_Formatter.JPG)


* Use Win32DiskImager install downloaded Armbian image to SD card<br>
使用Win32DiskImager将下载好的Armbian映像安装的到SD卡上<br>
![Win32DiskImager](https://github.com/Zhong-Github2020/orangepi/blob/main/Win32DiskImager.JPG)

* Start up nginx server
```
cd etc
nginx
```

* stop nginx server
```
nginx -s quit
```
another method to stop nginx<br>
另外一种停止nginx的方法<br>
查看进程号 -> 杀死进程
```
ps -ef|grep nginx
kill -QUIT 进程号
```
