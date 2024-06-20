官方下载地址
https://download.jetbrains.com/lcsrv/license-server-installer.zip


patch文件说明
目录 .jb-license-server 保存的是配置文件.
目录 conf 保存jvm启动参数,用于设置agent代理.
目录 ja-netfilter 为agent代理程序.


支持以下产品激活
IntelliJ IDEA Ultimate 2021.3.1
PyCharm 2021.3.1
Code With Me


使用方式
1.将下载的license-server-installer.zip解压到指定目录,比如 C:\tool\license-server\
将license-server-patch.zip内容也解压到同一目录 C:\tool\license-server\

2.cmd命令行下,切换到 license-server的 bin 目录 C:\tool\license-server\bin 执行以下命令,设置配置文件目录
license-server.bat configure --jb.license-server.base-dir=C:\tool\license-server\

3.启动服务
license-server.bat start



注意
1.由于一些规则限制,服务器端口必须为8080,不要修改默认端口.
2.如果要在jetbrains app测试,需要将服务器下 license-server/ja-netfilter/config/power.conf 规则,添加到你本地jetbrains app对于power.conf文件内.注意是添加,不要覆盖，以免导致你本地现在的配置丢失不能使用.
或者直接复制出ja-netfilter目录到本地使用.
3.在jetbrains app的对应server地址 http://ip:8080/ 进行激活.
4.授权登录地址请看auth.txt
5.license-server现在要求java 11以上版本运行
6.如果有问题可尝试重启服务
license-server.bat stop
license-server.bat start