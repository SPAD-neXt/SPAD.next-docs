# Saitek/Logitech MP/RP blinking

If your Saitek/Logitch devices are constanly activating for a short time even when SPAD.neXt is not runing, whenever you are activating a window or open the Start-Menu, this is caused by a Windows Service called "GameInput Service". \
Usually it gets installed and activated when you install MSFS via Steam, to enable the Steam-Remoteplay features. \
If you do not need this feature, you can get rid off that blinking:

* [ ] Start Services manager (Windows key "services")
* [ ] For the Services "GameInput Service"&#x20;
  * [ ] Stop the service if it is running
  * [ ] Set the Start-Type to "disabled"
* [ ] reboot computer
* [ ] It might be possibel to repeat this steps after a windows update or are the Steam-GameInput Redistributables are reinstalled
