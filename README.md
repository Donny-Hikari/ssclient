# Introduction / 介绍
This is a script service which will start shadowsocks and polipo automatically.  
自动开启Shadowsocks和Polipo的一个小脚本。  

# Preparation / 准备
+ Install shadowsocks / 安装Shadowsocks
```bash
sudo apt-get install shadowsocks
```
+ Install polipo / 安装Polipo
```bash
sudo apt-get install polipo
```
+ Install supervisor (Optional) / 安装Supervisor（可选）
```bash
sudo apt-get install supervisor
```

# Install / 安装
Use the following command to install this script:  
使用下面的命令来安装脚本：  
```bash
sudo cp ssclient /etc/init.d/
sudo chmod a+x /etc/init.d/ssclient
```

# Configuration / 设定
## Setting ports / 设置端口
Change the following variable to the ports you want.  
将下面的值改成你设定的端口。  
```bash
SHADOWSOCKS_PORT=108   #The port used by shadowsocks
POLIPO_PORT=1081       #The port used by polipo
```

Notice that if you edit the script after you copy it to /etc/init.d/ , a permission issue may occur. It's recommended to edit the script before copy it to /etc/init.d/ . If you want to edit the script from /etc/init.d/ , run the following command to grand the permission.  
请注意，如果你在将脚本拷贝到 /etc/init.d/ 后再编辑，可能会有权限问题。建议在拷贝前先设定好脚本。如果希望直接在 /etc/init.d/ 下编辑脚本，请运行下面的命令。  
```bash
sudo chown [your-username] /etc/init.d/ssclient
sudo chmod u+rwx /etc/init.d/ssclient
```

## Start it automatically at login / 使脚本在启动时自动运行
Use the following command to start this script automatically at login:  
下面的命令使脚本成为自动启动项：  
```bash
sudo update-rc.d ssclient defaults
```

# Supported Operation / 支持的操作
+ General service operation / 普通服务支援的操作
+ Use the following command to check the state of the ports:  
  使用下面的命令来查看端口状态：  
```bash
sudo service ssclient state
```

# Author / 作者
[![Donny](https://avatars.githubusercontent.com/u/22200374?v=3&s=150 "Donny")](https://github.com/Donny-Hikari)


