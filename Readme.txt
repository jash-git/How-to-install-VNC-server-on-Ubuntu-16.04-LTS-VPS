How to install VNC server on Ubuntu 16.04 LTS VPS [LINUX VPS 遠端桌面VNC 安裝教學]


GITHUB: https://github.com/jash-git/How-to-install-VNC-server-on-Ubuntu-16.04-LTS-VPS

資料來源:https://www.youtube.com/watch?v=f-NS4IM3NEI
https://vpsfix.com/5219/install-remote-desktop-vnc-ubuntu-16-04-server/

00.Update and upgrade.
    $apt update
    $apt upgrade

01.Following command will install latest Xfce desktop environment and the TightVNC package on your Ubuntu 16.04 VPS
    $apt install xfce4 xfce4-goodies tightvncserver

02.run following command to initiate initial configuration of VNC server.
    $vncserver
Note: You’ll be promoted to enter and verify a password. This is the password for root VNC user. It can be different from your server root password. You’ll be also asked for view-only password, you can ignore it by typing n.

03.install Synaptic Package Manager
    $apt install synaptic
    $apt update
    $apt upgrade	

04.Configuring the VNC Server
    $vncserver -kill :1
    $mv ~/.vnc/xstartup ~/.vnc/xstartup.bak
    $nano ~/.vnc/xstartup
        Paste following lot,
            #!/bin/bash
            xrdb $HOME/.Xresources
            startxfce4 &
    $chmod +x ~/.vnc/xstartup
    
05.Start VNC server
    $vncserver