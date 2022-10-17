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
However, this will draw the full 500ms per deviceport from the hub. Therefor it is **important** to follow the best practices.
