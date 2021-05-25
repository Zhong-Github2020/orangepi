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

* Start up ngrok XiaoMiQiu
```
 ./ngrok -config ngrok.conf -log=ngrok.log start httptun httpstun tcptun
```
If the ngrok service is close after terminal close, then use nohup
```
nohup ./ngrok -config ngrok.conf -log=ngrok.log start tcptun
```

After that, we can remote login this machine via below:
```
ssh -p 91 user@user128.ngrok2.xiaomiqiu.cn
```

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

向vsftp服务器上传文件报“550 Permission denied”错误的解决办法 <br>

原因：vsftp默认配置不允许上传文件。 <br>
解决：修改/etc/vsftpd.conf <br>
将“write_enable=YES”前面的#取消。 <br>
