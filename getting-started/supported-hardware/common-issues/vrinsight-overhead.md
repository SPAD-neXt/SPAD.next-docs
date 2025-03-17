---
description: Common Issues with VRInsight Overheads
---

# VRInsight Overhead

Do enable the Overhead in SPAD.neXt add the serial port as new serial device and select VRInsight as protocol.

* Newer hardware versions have **fake** knobs for e.g. Temp and Breakers. Those are **not** wired&#x20;
* Firmware is kind of buggy. Upon first connect it will somtimes overflow the serial port and SPAD.neXt will not recognize it. Click the connect button again and it will connect.&#x20;
* Sometimes the Firmware dies and is not responding to commands anymore. This is due to the clunky protocol of VRi. \
  Solution: Unplug USB **and** power , replug power , wait 15 secs, replug usb&#x20;

