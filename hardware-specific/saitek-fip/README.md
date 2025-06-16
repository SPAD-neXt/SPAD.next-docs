---
description: Special notes about Saitek FIP requirements and support
---

# Saitek FIP (Flight Instrument Panel)

For SPAD.neXt to handle the Saitek/Logitec FIP correctly the following steps need to be performed:

* Install the Saitek FIP Drivers. (Download at their webpage)
* After installation, uninstall the "DirectOutput Service"
* MSFS: Uninstall the the Logitec "Flightsimulator Plugin"

For best practices about FIP connection to your PC please see [https://fipgauges.com/hardware.php](https://fipgauges.com/hardware.php)

Please note, in contrast to the original Saitek implementation, which limits updates to one device at a time , SPAD.neXt will drive all FIP at full speed with concurrent updates, resulting in up to 16fps per device.\
However, this will draw the full 500mA per deviceport from the hub. Therefor it is **important** to follow the best practices.

SPAD.neXt supplies the standard saitek gauges that come with the FIP. For more sophisticated gauges it's recommend to have a look at [fipgauges.com](https://fipgauges.com) or [Fsx times](https://fsxtimes.wordpress.com/category/gauges/)\
Also there are some user created gauges available inside SPAD.neXt

### Error Rendering on Device

This is indicates the device is not getting enough usb power to keep up rendering.\
See [HUB requirements ](../usb-hub-requirements.md)and the best practice above
