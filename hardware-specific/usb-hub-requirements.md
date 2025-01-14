# USB HUB Requirements



1. Power in A needed = Devices connected \* 0.5
2. Normal (cheap china) hub usually do **not** provide a power adaptor to drive **all** it's ports at the same time. (They usually assume only 50% of the ports will be drawing power at the same time). You will usually see that they provide like 1.5-2A for a 6 port hub. That is not enough if you have 6 flight devices connected.
3. Every device that has some kind of display (Fip, radio panel , multipanel , even a Bravo (leds) ) will _constantly_ pull 500mA of the hub-psu
4. Rule of thumb is to have a psu that provides Devices\*0.5A + 0.5A , to kinda ensure the psu is not falling down if max is pulled of it. (Again cheap power adaptors tend not to be able to provide their max output value constantly, especially right after power on). \
   It's like a car... it can only drive full power so long, and then it will slow down because everything is overheating and loosing effectivness
5. If you connect a **unpowered** hub to your computer (shame on you!) it will be able to drive **exactly** one device. Not more.
6. Also connecting 5 fip to **one** usb 2.0 hub will most likely faila s well, due to usb 2.0 bandwidth limitations. All devices connected to the hub **share** the bandwidth.
