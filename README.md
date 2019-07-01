# vnc

vi ~/.vnc/xstartup 
裡面的最後一行拿掉, 這是tigervnc的bug
https://bugs.centos.org/view.php?id=15667

另外, 安裝xorg-x11-twm-1.0.9-6.el7.x86_64.rpm 
xstartup 底下添加兩行
xterm-geometry 80x24+10+10 -ls -title "$VNCDESKTOP Desktop"&;
twm & 

==> xstartup 內容
#!/bin/sh

unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS
/etc/X11/xinit/xinitrc
xterm-geometry 80x24+10+10 -ls -title "$VNCDESKTOP Desktop"&;
twm &
#vncserver -kill $DISPLAY
