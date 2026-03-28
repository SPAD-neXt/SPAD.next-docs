# CDU Devices

SPAD.neXt supports a wide range of hardware CDU devices, to display aircraft CDU/FMC on it. Since there is no standard defined every aircraft has to be implemented manually.

You can use snippet #13161 / #13165 for a reference implementation of CDU's

{% hint style="danger" %}
All CDU devices are a complete edition feature
{% endhint %}

## Currently supported aircraft

### MSFS/MSFS24

* Aerosoft CRJ
* Fenix - All Aircarft
* FlyByWire - SimBridge must be running
* FsLabs
* iFLY 737
* Inibuilds A340 (MSFS 2024 Only)
* MaddogX
* PMDG - All aircraft. [SDK must be enabled](../getting-started/untitled/simulation-specifc-steps/msfs-enable-pmdg-data-access.md)
* TFDI MD11/B717
* z-dementedmonkey Mod (v0.10.0 March 2026) SPAD.neXt v0.9.24 required
  * [Download Link to DM Github](https://github.com/dementedmonkey/cj4-mcdu)
    * **MSFS 2020 Supported Aircraft**:
      * Citation CJ4 - Working Title (This is the Default CJ4 since 2020 AAU1)
      * FFX P180 v2.0.3 (Read dementedmonkey mod instructions about additional package installation process) - Remove any z-lim-ffx-cdu mods
      * FFX C750 v1.3.9 - Remove any z-lim-ffx-cdu mods
    * **MSFS 2024 Supported Aircraft:**
      * 737 Max 8 - Asobo (Default Sim Plane)
      * Citation CJ4 - Working Title (Default Sim Plane - WT21v2)
      * C90 King Air - MS/Carenado (Default Sim Plane - WT21v2)
      * FFX C750 v1.3.9 (Still using the v1 Avionics Fork) - Remove any z-lim-ffx-cdu mods
      * FFX P180 v2.1.9 (WT21v2) - Remove any z-lim-ffx-cdu mods<br>

### FSX/P3D

* PMDG - All aircraftt. SDK must be enabled&#x20;
* iFLY

### X-Plane

* all aircraft that use the X-Plane standard cdu datarefs
* ToLiss aircraft
* ZiBO mod
* Rotate MD-11
* Rotate MD-80
  * The MD-80 has a 30 characters wide display, while CDU devices only have 24 character per line.\
    Only the first 12 and last 12 characters will be shown on the device.
  * The horizontal/vertical lines are currently not supported
* CL650
* FF 767 / 757
* FF 777v2



## CDU Devices with HDMI Interface

To drive CDU devices with a HDMI connector through SPAD.neXt to get access to all extended features without needing to popout a window in the simulator, SPAD.neXt provides a RemoteCDUDisplay-Tool which will popout a customizable window.

You can use snippet #13161 / #13165 for a reference implementation

&#x20;The tool can be found in the SPAD.neXt installation directory in the subfolder Tools/cdu. It can be run on a remote computer if necessary

* to run display upon load of a profile create a `profile loaded` event and run the external command "\<spad\_install\_dir>/tools/cdu/RemoteCDUDisplay.exe" or add it to a batch-file
* To run the display on a remote computer copy tools/cdu to target computer, and start "RemoteCDUDisplay.exe -h=ipOfSPAD -p=28001 -t=`targetid`". To get the targetid open the cdu tool once using SPAD.neXt.

## WinCTRL CDU Devices

{% hint style="danger" %}
WinCTRL CDU Devices must be configured in SimAppPro as CAPTAIN, you can select to show the FO-Side inside SPAD.neXt then.
{% endhint %}

Updating the CDU Font is currently not supported. Update the font using SimAppPro

