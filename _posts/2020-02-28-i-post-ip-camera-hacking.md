---
layout: default
title: IP Camera BAT 310 Hacking
dd: ipcamerabat310
category: timeline
tags: article
---

Got a Solar WiFi IP camera from <a href="https://www.ebay.com.au/itm/302918525683?ul_noapp=true">Wireless Solar IP67 Security Camera System Outdoor Home Cam 1080P 2MP</a>

Wondering to control this camera using script/program. 

To activate/wakeup, the camera has to be set correctly:
1.	The camera is connected to the Internet, and its status should be shown as ‘online’ on Microshare, Danale mobile client. 


Active the camera using python script:
```python
import socket, sys
import binascii
dest = ('camera ip address', 'any port)
# sending these hex code  in UDP protocal to active camera
packet = binascii.unhexlify("0000000a983b16f8f39c")
s=socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
s.setsockopt(socket.SOL_SOCKET, socket.SO_BROADCAST, 1)
s.sendto(bytes(packet), dest)
```


