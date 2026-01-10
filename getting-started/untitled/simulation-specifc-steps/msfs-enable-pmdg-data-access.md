# MSFS: Enable PMDG data access

{% hint style="warning" %}
Steps provided for the PMDG 737, for all other PMDG aircraft same steps epply for the aircrafr specific ini-file
{% endhint %}

To access MSFS PMDG Data from SPAD.neXt the following steps have to be completed:<br>

1. In MSFS the PMDG 737 must have been loaded beyond "ready to fly" at least once and exited again.
2. Exit MSFS
3.  in Windows File-Explorer open&#x20;

    1. For MSFS 2020\
       Store/Gamepass Version \
       `%LOCALAPPDATA%\Packages\Microsoft.FlightSimulator_8wekyb3d8bbwe\LocalState\packages\pmdg-aircraft-737\work` \
       Steam Version \
       `%APPDATA%\Microsoft Flight Simulator\Packages\pmdg-aircraft-737\work`
    2. For MSFS 2024

    `%LOCALAPPDATA%/Packages/Microsoft.Limitless_8wekyb3d8bbwe/LocalState/WASM/pmdg-aircraft-737\work`
4. Add to end of 737\_Options.ini

`[SDK]` \
`EnableDataBroadcast=1` \
`EnableCDUBroadcast.0=1` \
`EnableCDUBroadcast.1=1`<br>

{% hint style="info" %}
The EnableCDUBroadcast entries are only needed if you have a CDU Device or want to access CDU Data within SPAD.neXt

Add `EnableCDUBroadcast.1=1` additionally to get access to the center cdu (e.g. 777)
{% endhint %}

{% hint style="danger" %}
Make sure there is a newline/empty line after the last entry in the ini file and after each block, else it will get deleted again by the pmdg
{% endhint %}

1. start MSFS and load 737, start flight
2. start SPAD.neXt
3. Make sure in SPAD.neXt\
   Settings->Status\
   PMDG Connection shows as connected. \
   If it's not connected check the ini file.
4. Always 3 green!

All SDK Data and events are referenced in SPAD.neXt in the  "PMDG 737 NGXu" category



P3D PMDG 737 NGXu SPAD.neXt Profiles will be working.

{% hint style="danger" %}
Please note PMDG Simulation Events work exactly like the cockpit. Use the "PMDG Special Actions" to do with the event what you would do in cockpit with the mouse!
{% endhint %}
