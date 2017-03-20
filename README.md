# Introduction
This is a script service which will start shadowsocks and polipo automatically.

# Preparation
+ Install shadowsocks
```bash
sudo apt-get install shadowsocks
```
+ Install polipo
```bash
sudo apt-get install polipo
```
+ Install supervisor (Optional)
```bash
sudo apt-get install supervisor
```

# Install
Use the following command to install this script:
```bash
sudo cp ssclient /etc/init.d/
sudo chmod a+x /etc/init.d/ssclient
```

# Configuration
## Setting ports
Change the following variable to the ports you want.
```bash
SHADOWSOCKS_PORT=108   #The port used by shadowsocks
POLIPO_PORT=1081       #The port used by polipo
```

Notice that if you edit the script after you copy it to /etc/init.d/ , a permission issue may occur. It's recommended to edit the script before copy it to /etc/init.d/ . If you want to edit the script from /etc/init.d/ , run the following command to grand the permission.
```bash
sudo chown [your-username] /etc/init.d/ssclient
sudo chmod u+rwx /etc/init.d/ssclient
```

## Start it automatically at login
Use the following command to start this script automatically at login:
```bash
sudo update-rc.d ssclient defaults
```

# Supported Operation
+ General service operation
+ Use the following command to check the state of the ports:
```bash
sudo service ssclient state
```

# Author
[![Donny](https://avatars.githubusercontent.com/u/22200374?v=3&s=150 "Donny")](https://github.com/Donny-Hikari)


