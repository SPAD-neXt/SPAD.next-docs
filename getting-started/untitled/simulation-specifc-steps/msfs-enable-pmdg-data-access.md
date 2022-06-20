# MSFS: Enable PMDG data access

To access MSFS PMDG Data from SPAD.neXt the following steps have to be completed:

1. In MSFS the 737 must have been loaded beyond "ready to fly" at least once and exited again.
2. Exit MSFS
3. in file browser open \
   Store/Gamepass Version \
   `%LOCALAPPDATA%\Packages\Microsoft.FlightSimulator_8wekyb3d8bbwe\LocalState\packages\pmdg-aircraft-737\work` \
   ``Steam Version \
   `%APPDATA%\Microsoft Flight Simulator\Packages\pmdg-aircraft-737\work`
4. Add to end of 737\_Options.ini

`[SDK]` \
`EnableDataBroadcast=1` \
`EnableCDUBroadcast.0=1` \
`EnableCDUBroadcast.1=1`\
``

{% hint style="danger" %}
Make sure there is a newline/empty line after the last entry, eöse it will get deleted again
{% endhint %}

1. start MSFS and load 737, start flight
2. start SPAD.neXt
3. Make sure in SPAD.neXt\
   Settings->Application->FSX (SPAD.neXt 0.9.12 Alpha) \
   Settings->Application->Simulations (SPAD.neXt 0.9.11.5) \
   PMDG Support is enabled. (If it was not, enable it and restart SPAD.neXt)
4. Always 3 green!

* All Data in "PMDG 737 NGXu" should be working
* All Simulation Events in "PMDG 737 NGXu" should be working.
* Cockpitmaster CDU should be working right away

P3D PMDG 737 NGXu SPAD.neXt Profiles should be working.

Please remember PMDG Simulation Events work exactly like the cockpit. Use the "PMDG Special Actions" to do with the event what you would do in cockpit with the mouse!
