---
description: Virtual Power Support for serial devices
---

# Device Virtual Power

To enable Virtual Power support for the device, the following steps have to be done:

* [ ] Add the Option VPSUPPORT=1
* [ ] Define an INPUT with
  * [ ] DeviceIndex 0
  * [ ] Type `SYSTEM`
  * [ ] Tag `CONFIGURE_PANEL_STATUS`&#x20;
  * [ ] Inherit `SPAD_VIRTUAL_POWER`&#x20;
  * [ ] OPTION `UI_TYPE=3 CUSTOM_TYPE=POWER`
  * [ ] (in Alpha < 0.9.12.38) `WIDTH=20 HEIGHT=20`

This will add the SPAD.neXt standard power-configuration button to the device UI, and the device will be treated like any other device that supports virtual power.

Example

`0,INPUT,0,CONFIGURE_PANEL_STATUS,SYSTEM,SPAD_VIRTUAL_POWER,UI_TYPE=3,CUSTOM_TYPE=POWER`

``
