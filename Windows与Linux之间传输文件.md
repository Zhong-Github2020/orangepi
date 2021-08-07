### 当windows与linux处于同一局域网，通过ftp传输文件到linux服务器
在windows的文件管理器的地址栏输入：
```
ftp://192.168.x.xxx/
```
<br>
### 当windows在外网通过ngrok穿透时，通过SSH传输文件到linux服务器

在Powershell下可以用scp这个命令来通过ssh传输文件。<br>
但下述指令是在powershell下进行，不需要通过ssh登录远程服务器。
```
PS C:\Users\xxx>
``` 
需要注意的是对于windows的SCP来说，其默认目录为C:\User\xxx\ （可以通过在powershell的输入"dir"或者"ls"来观察）

1. 从服务器上下载文件
scp username@servername:/path/filename /var/www/local_dir（本地目录）

 例如：
```
PS C:\Users\xxx>scp -P 91 xxx@xxx128.ngrok2.xiaomiqiu.cn:/home/xxx/ftp/startngrok.txt Desktop/
```
 把xxx128.ngrok2.xiaomiqiu.cn上的/home/xxx/ftp/startngrok.txt 的文件下载到/Desktop（本地目录）<br>
 上面的"-P 91"是将ngrok内网穿透的端口指定。


2. 上传本地文件到服务器
scp /path/filename username@servername:/path   

 例如:
```
PS C:\Users\xxx>scp -P 91 Desktop/startngrok.txt xxx@xxx128.ngrok2.xiaomiqiu.cn:/home/xxx/ftp/
```
 把本机/Desktop/目录下的startngrok.txt文件上传到xxx128.ngrok2.xiaomiqiu.cn这台服务器上的/home/xxx/ftp/目录中<br>
 上面的"-P 91"是将ngrok内网穿透的端口指定。
 

3. 从服务器下载整个目录
scp -r username@servername:/var/www/remote_dir/（远程目录） /var/www/local_dir（本地目录）<br>

 例如

4. 上传目录到服务器
scp  -r local_dir username@servername:remote_dir<br>

 例如
