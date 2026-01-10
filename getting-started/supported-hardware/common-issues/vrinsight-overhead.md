---
description: Common Issues with VRInsight Devices
---

# VRInsight Devices

Do enable the support of a VRInsight device in SPAD.neXt add the serial port as new serial device (Settings->Devices->Sertial Devices) and select **VRInsight** as protocol.

* Newer hardware versions of the overheads have **fake** knobs for e.g. Temp and Breakers. Those are **not** wired&#x20;
* Firmware is kind of "strange". Upon first connect it will somtimes overflow the serial port and SPAD.neXt will not recognize it. Click the connect button in the SPAD.next UI again and it will connect.&#x20;
* Sometimes the Firmware dies and is not responding to commands anymore. \
  Solution: Unplug USB **and** power , replug power , wait 15 secs, replug usb&#x20;

