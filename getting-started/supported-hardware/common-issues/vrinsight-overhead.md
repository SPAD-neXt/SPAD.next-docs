---
description: Common Issues with VRInsight Overheads
---

# VRInsight Overhead

* Newer hardware versions have **fake** knobs for e.g. Temp and Breakers. Those are **not** wired&#x20;
* Firmware is kind of buggy. Upon first connect it will somtimes overflow the serial port and SPAD.neXt will not recognize it. Click the connect button again and it will connect.&#x20;
* Sometimes the Firmware dies and is not responding to commands anymore. This is due to the clunky protocol of VRi. \
  Solution: Unplug USB **and** power , replug power , wait 15 secs, replug usb&#x20;
* When flipping the Power-Switch Off-On, the device will send all switch states to SPAD.neXt Currently you cannot prevent events being executed (working on a solution), so advise is to do that before starting a flight to have UI and device synced.
