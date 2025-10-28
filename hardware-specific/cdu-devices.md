# CDU Devices

SPAD.neXt supports a wide range of hardware CDU devices, to display aircraft CDU/FMC on it. Since there is no standard defined every aircraft has to be implemented manually.

## Currently supported aircraft

### MSFS/MSFS24

* PMDG - All aircraft. [SDK must be enabled](../getting-started/untitled/simulation-specifc-steps/msfs-enable-pmdg-data-access.md)
* Aerosoft CRJ
* Fenix - All Aircarft
* FsLabs
* MaddogX
* TFDI MD11/B717
* iFLY
* FlyByWire - SimBridge must be running
* [CT WT21 Mod](https://github.com/dementedmonkey/cj4-mcdu) - V0.7 / 0.8 (Default CJ4, C90, 737 MAX)
* [FFX P180 / FFX C750 Citation X](https://www.dropbox.com/scl/fi/ho9w7by5umnf7xywev5ru/lim-ffx-cdu-1.0.12.zip?rlkey=g5pr1ndb3vr4t2ni2euifa3ye\&dl=0)

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
    Online the first 12 and last 12 characters will be schon on the device.
* CL650
* FF 767 / 757
* FF 777v2



## CDU Devices with HDMI Interface

To drive CDU devices with a HDMI connector through SPAD.neXt to get access to all extended features without needing to popout a window in the simulator, SPAD.neXt provides a RemoteCDUDisplay-Tool which will popout a customizable window.

You can use snippet #13161 / #13165 for a reference implementation

&#x20;The tool can be found in the SPAD.neXt installation directory in the subfolder Tools/cdu. It can be run on a remote computer if necessary

* to run display upon load of a profile create a `profile loaded` event and run the external command "\<spad\_install\_dir>/tools/cdu/RemoteCDUDisplay.exe" or add it to a batch-file
* To run the display on a remote computer copy tools/cdu to target computer, and start "RemoteCDUDisplay.exe -h=ipOfSPAD -p=28001"

## WinWing CDU Devices

{% hint style="danger" %}
WinWing CDU Devices must be configured in SimAppPro as CAPTAIN, you can select to show the FO-Side insde SPAD.neXt then.
{% endhint %}

Updating the CDU Font is currently not supported. Update the font using SimAppPro

