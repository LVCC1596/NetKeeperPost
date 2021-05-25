# 用于本地拦截NetKeeper账号并提交到路由器

## 需要安装 [winpacp](https://www.winpcap.org/install/bin/WinPcap_4_1_3.exe)

### 用到的库  Scapy
* pip install scapy
### 使用 
* 运行 FakePPPoe.py 然后根据提示来.
* 记得把代码里的路由器网址改成自己的默认写的 192.168.0.1.
* 路由器拨号用户名改为 abcdefghijklmn123(也可以自己改，主要是为了替换请求里的数据),密码填写正确的密码即可.

### 自动POST路由器原理
* 使用Scapy 获取路由器点击拨号发送的请求参数(所以需要先登陆路由器点一下拨号),然后替换请求体里的账号，在进行数据拼装发送。
* 并不是拦截数据改
* 如果路由器使用HTTPS协议的话自动提交将无法使用,可以参照Config.txt文件把路由器发送的参数写进去，使用RouterPost.py这个文件提交
### 一些问题 
* 1.提交之后可能不会自动拨号需要手动点一下拨号，请根据路由器联网状态自行判断.
* 2.某些路由器固件不支持\r，无法拨号.
* 3.我觉得这个方法可以适用大部分路由器,但是我没那么多路由器测试😂
* 4.如果帮到你了,你也帮我点个Star🌟吧!