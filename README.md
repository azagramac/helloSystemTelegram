## Send message notification Telegram on boot

### Requeriments
- Raspberry Pi / NanoPi
- [Raspbian OS](https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit) / [DietPi](https://dietpi.com/#download) / [ARMbian](https://www.armbian.com/download/)
- Token and chat_id of your telegram bot, you can request them here from Telegram App: 
- Bot token: https://t.me/botfather
- Chat_ID: https://t.me/myidbot

### Install packages
    sudo apt update
    sudo apt upgrade -y
    sudo apt curl -y

### Edit hello.service file to change the path where you have the hello.sh script.
    ExecStart=/usr/bin/bash	/root/hello.sh

### Copy the hello.service and assign it the permissions 0644
    cp hello.service /etc/systemd/system/
    chmod 0644 /etc/systemd/system/

### Restart service, and enabled
    systemctl daemon-reload
    systemctl enable hello.service

### Edit the script hello.sh, to add your bot token, and your chat_id, rename the chosen script to hello.sh 
    TOKEN_BOT="YOUR_TOKEN_BOT"
    TOKEN_ID="YOUR_TOKEN_CHAT"

### Assign it the permissions a+x
    chmod a+x /root/hello.sh

### Ready!
![NanoPi](https://github.com/AzagraMac/helloSystemTelegram/blob/master/res/msg_nanopi.png)

![RaspberryPi](https://github.com/AzagraMac/helloSystemTelegram/blob/master/res/msg_raspberrypi.png)

