# Saitek/Logitech MP/RP blinking

If your Saitek/Logitch devices are constanly activating for a short time even when SPAD.neXt is not runing, whenever you are activating a window or open the Start-Menu, this is caused by a Windows Service called "GamingServices". \
Usually it gets installed and activated when you install MSFS via Steam, to enable the Steam-Remoteplay features. \
If you do not need this feature, you can get rid off that blinking:

* [ ] Start the "Registry Editior"
* [ ] Move to "HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControlSet\Services\GamingServices"
* [ ] delete the Subkey "Security"
* [ ] Move to "HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControlSet\Services\GamingServicesNet"
* [ ] delete the Subkey "Security"
* [ ] reboot computer
* [ ] Start a Administrator Command-Prompt (WindowsKey "cmd" -> Run as Administrator)
* [ ] Enter the commands
  * [ ] `sc triggerinfo GamingServices delete`
  * [ ] `sc triggerinfo GamingServicesNet delete`
* [ ] Start Services manager (Windows key "services")
* [ ] For the Services "GameInput Service" and  "Gaming Service" (2 entries!)
  * [ ] Stop the service if it is running
  * [ ] Set the Start-Type to "disabled"
* [ ] reboot computer
* [ ] It might be possibel to repeat this steps after a windows update or are the Steam-GameInput Redistributables are reinstalled
