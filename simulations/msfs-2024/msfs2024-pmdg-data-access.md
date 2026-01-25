---
description: How to enable PMDG data access in MSFS 2024
---

# MSFS2024 PMDG Data Access

{% hint style="warning" %}
Steps provided for the PMDG 737, for all other PMDG aircraft same steps apply for the aircrafr specific ini-file
{% endhint %}

To access MSFS2024 PMDG Data from SPAD.neXt the following steps have to be completed:<br>

* [ ] In MSFS2024 the PMDG 737 must have been loaded beyond "ready to fly" at least once and exited again.
* [ ] Exit MSFS2024
* [ ] in Windows File-Explorer open
  * [ ] Store/Gamepass Version \
    %LOCALAPPDATA%\Packages\Microsoft.Limitless\_8wekyb3d8bbwe\LocalState\WASM\MSFS2024`\pmdg-aircraft-737\work`&#x20;
  *   [ ] Steam Version \
      %APPDATA%\Microsoft Flight Simulator 2024\WASM\MSFS2024\pmdg-aircraft-738\work\\


* [ ] Add to end of 737\_Options.ini

`[SDK]` \
`EnableDataBroadcast=1` \
`EnableCDUBroadcast.0=1` \
`EnableCDUBroadcast.1=1`<br>

{% hint style="info" %}
The EnableCDUBroadcast entries are only needed if you have a CDU Device or want to access CDU Data within SPAD.neXt

Add `EnableCDUBroadcast.2=1` additionally to get access to the center cdu (e.g. 777)
{% endhint %}

{% hint style="danger" %}
Make sure there is a newline/empty line after the last entry in the ini file and after each block, else it will get deleted again by the PMDG
{% endhint %}

* [ ] start MSFS2024 and load 737, start flight
* [ ] exit MSFS2024
* [ ] start MSFS2024 and load 737, start flight
* [ ] start SPAD.neXt
* [ ] Make sure in SPAD.neXt\
  Settings->Status\
  PMDGNG3 Connection shows as connected. \
  If it's not connected check the ini file, also make sure that you restarted MSFS at went beyond the  "ready to fly" screen after making any changes to the pmdg ini files.
* [ ] Always 3 green!

All SDK Data and events are referenced in SPAD.neXt in the  "PMDG 737 NGXu" (PMDGNG3) category



{% hint style="danger" %}
Please note PMDG Simulation Events work exactly like the cockpit. Use the "PMDG Special Actions" to do with the event what you would do in cockpit with the mouse!\
In MSFS 2024 PMDG applyed some changes and some functions can only be triggered viy LVAR now
{% endhint %}
