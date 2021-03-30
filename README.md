## Send message notification Telegram on boot

### Requeriments
- Raspberry Pi / NanoPi
- [Raspbian OS](https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit) / [DietPi](https://dietpi.com/#download) / [ARMbian](https://www.armbian.com/download/)

### Install packages
    sudo apt update
    sudo apt upgrade -y
    sudo apt curl -y

### Edit hello.service
Edit the hello.service file to change the path where you have the hello.sh script.
    ExecStart=/usr/bin/bash	/root/hello.sh

### Copy the hello.service and assign it the permissions 0644
    cp hello.service /etc/systemd/system/
    chmod 0644 /etc/systemd/system/

### Restart service, and enabled
    systemctl daemon-reload
    systemctl enable hello.service

### Assign it the permissions a+x
    chmod a+x /root/hello.sh

### Ready!
Sample for NanoPi:
![NanoPi](https://github.com/AzagraMac/helloSystemTelegram/blob/master/res/msg_nanopi.png)

Sample for RaspberryPi:
![RaspberryPi](https://github.com/AzagraMac/helloSystemTelegram/blob/master/res/msg_raspberrypi.png)

