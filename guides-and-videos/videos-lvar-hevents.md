---
description: >-
  This Section is focused on L:VARs, H and B Events ...  These are the more
  customized items per plane and delve deeper into the programing of custom
  events and finding them.
---

# L:Vars / H:Events and B:Events

L:VARs and H:Events are additional Variables and Sim Control events that are not part of the "Standard" events in Sim connect.  This requires an Additional Bridge be installed. \
\
In both Prepar3d and MSFS L:VARs are required so we can work with the Extended capabilities of Add On Aircraft.  This is how all of the complex aircraft will interact data wise for their custom systems implementations.  The most notable being Auto Pilot Data.  Add On Planes need to run their own systems to simulate the modes and functions of the simulation.  Then they "under the hood" take control of the plane and fly it.... Thus we need to gain access to View and Control that Data!\
\
The H:Event is the new JS/HTML Gauge Events found in MSFS which also replaced many of the older simconnect events like the GPS controls commands.  MODs like the  Working Title CJ4 and the Fly By Wire A320 have also required the separation of the Standard Autopilot and Data to allow them to implement their controls.  This meant modifying the commands and Data.  We are able via the Bridge to also send these Commands into the sim.  Additional names in use for this will be WASM Bridge or WASM Module.\
\
If you are interested in understanding all of the different data types the SDK docs are valuable source of info.  [https://docs.flightsimulator.com/html/index.htm#t=Additional\_Information%2FReverse\_Polish\_Notation.htm%23Types](https://docs.flightsimulator.com/html/index.htm#t=Additional_Information%2FReverse_Polish_Notation.htm%23Types)\


MSFS 2020 and MSFS 2024 Require the L:VAR Bridge to function properly. This is also the H:Event Gateway as those have to be done via the WASM Module as well. In FSX/P3D it is not "required" unless you are using advanced planes.. which well makes it required. Also same Wizard area for installing the XPlane Plugin. Bonus: How to Relocate your community folder!

{% embed url="https://youtu.be/56Q7yKfIjkE" %}
Install the L:VAR Bridge and Move 2024 Community Folder
{% endembed %}

One of the early examples of working with L:VARs and Add On Aircraft

{% embed url="https://youtu.be/hSO2RkXNOvI" %}
Getting Started with L:Vars using the CRJ
{% endembed %}

Client Events.  How to Add custom events that are not currently in the SPAD.neXt Event List.

{% embed url="https://youtu.be/Tw53OCbGvQg" %}
Add H:Events or K:Events Manually
{% endembed %}



L:VAR control to work around some conflicts of WT GNS and TDS GTN integrations.

{% embed url="https://youtu.be/cTnzSreUoSs" %}
Disable WT GNS LVARS to Run TDS External Mode
{% endembed %}

Working with Another Add On Airplane example.  The MS ATR and L:VARs to take control of the entire plane!

{% embed url="https://youtu.be/6jvi3-dWNQs" %}
Find The Control L:VARs via the Data Monitor
{% endembed %}

Dev Mode in MSFS can help you discover the Events/Vars used by each plane.  If the plane is encrypted and the XML locked out.. just use Dev Mode!

{% embed url="https://youtu.be/w9Wgk9cp05E" %}
XML or Dev Mode - Find H:Events
{% endembed %}

L:VAR example to create a button to "rebuild" the Engine on the SWS Kodiak!

{% embed url="https://youtu.be/Gwb3Bqpg2Tg" %}
Kodiak Engine Reset - LVars and Events
{% endembed %}

B:Events are finally Accessible (sure we are limited to \_SET for now due to MSFS limitations..) and this video is the first covering of this new feature!

{% embed url="https://youtu.be/QKlOUs-xtns" %}
B:Events Now Available -- How To Find and Use Them!
{% endembed %}

