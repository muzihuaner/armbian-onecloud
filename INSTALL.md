基于官方Armbian源码编译
感谢hzyitc等开发者为玩客云添加官方源码支持并修复了多项Bug  
https://github.com/hzyitc/armbian-onecloud


系统特点：支持HDMI、双USB，默认不安装docker可自行安装只需执行 apt install docker.io 命令即可。

刷入方法：解压固件包，使用USB线一头连接玩客云靠近hdmi接口的usb接口，一头连接至电脑，台式机请连接后面的USB口，暂时不要通电！

安装并打开 USB Burning Tool，导入 img 镜像，勾选 “擦除flash” 和 “擦除bootloader” 并点击 “开始”，短接刷机触点或者按住复位键的同时给玩客云通电，即可使用Aml Burn Tool软件直接烧录固件至玩客云。
初始账号密码  root   1234

(特别注意：USB Burning Tool 请使用2.1.6.8版本，其他版本可能出现超时等报错）


刷机包下载地址：https://github.com/hzyitc/armbian-onecloud/releases 注意后缀带Burn的才是直刷包，其他都是USB启动包。

如果Github下载较慢，以下是镜像下载链接（包括刷机软件）：

线刷工具USB Burning Tool  
https://ghproxy.com/https://github.com/muzihuaner/armbian-onecloud/releases/download/tools/Amlogic.USB.Burning.Tool.v2.1.6.8.exe
Ubuntu22.04(jammy)      

Debian11(bullseye)

