---
description: Videos Focused on the PMDG 737 for MSFS
---

# PMDG 737 (MSFS)

### Enable SDK in PMDG aircraft

1. The PMDG 737 in MSFS **must** have been loaded beyond "ready to fly" at least once and exited again.
2. Exit MSFS
3. In Windows File Browser open \
   Store/Gamepass Version \
   `%LOCALAPPDATA%\Packages\Microsoft.FlightSimulator_8wekyb3d8bbwe\LocalState\packages\pmdg-aircraft-737\work` \
   Steam Version \
   `%APPDATA%\Microsoft Flight Simulator\Packages\pmdg-aircraft-737\work` \
   For the 737-600 the folder is "pmdg-aircraft-736"
4. Add to end of 737\_Options.ini\
   `[SDK]` \
   `EnableDataBroadcast=1` \
   \
   If you have a CDU device also add \
   \
   `EnableCDUBroadcast.0=1` \
   `EnableCDUBroadcast.1=1`\
   \
   to the SDK section\
   **Make sure there is a newline/empty line after the section you added!**\

5. start MSFS and load 737 ,start flight
6. start SPAD.neXt
7. Check in SPAD.neXt that Settings->Status shows the PMDG Provider as connected
8. Always 3 green!

Please remember PMDG Simulation Events work **exactly** like the cockpit. \
Use the "PMDG Special Actions" to do with the event what you would do in cockpit with the mouse! Events from the Category **PMDG 737 NGXu** must be used.

### Video Guides

In the first Video we step through the requirements for Configuring the PMDG SDK and the SPAD.neXt Simulation Settings.  We also show how the Custom Interactive SDK interface to configure Data Vars and use the Event System unique to the PMDGs

{% embed url="https://youtu.be/TSBINY5rnn8" %}
First Step - Configure PMDG SDK and SPAD.neXt
{% endembed %}

In The Second Video for the PMDG 737 in MSFS we delve into adding the Cockpit Master CDU to SPAD.neXt and downloading the default Snippet to get full control over the the in sim CDUs.

{% embed url="https://youtu.be/QwK6ez8JtzE" %}
PMDG 737 (MSFS) and the Cockpit Master CDU
{% endembed %}

The Third Video for the 737 PMDG focuses on Programing the MCP (mode control support).  We delve into how the SDK works regarding Buttons / Switches / Knobs and Encoders with regards to the PMDG Interaction Events.  Also how to find and Map LEDs to Annunciators and Displays to Values!!

{% embed url="https://youtu.be/3_UmS1lSQPQ" %}
Configure 737 MCP Devices to Control the PMDG 737 MCP
{% endembed %}

Continuing on in the 4th PMDG 737 Video we configure the Honeycomb Bravo for use with the MCP (AP functions) as well as all other Axis and Switches!!  Full implementation of the LEDs and Annunciators -- don't forget you need to be on the at least 0.9.12.37 for this!!

{% embed url="https://youtu.be/Sc1HH0n8h_A" %}
Configure the Bravo TQ for the PMDG 737
{% endembed %}

Sticking with Autopilot Configurations we move on to the Logitech/Saitek Multi Panel device.  Download the Snippet or use the walkthrough to configure it yourself.

{% embed url="https://youtu.be/RVTOqQVL5pQ" %}
Configure the MultiPanel for the PMDG 737(MSFS)
{% endembed %}

In this Video we delve into the Thrustmaster TCA Airbus 320 TQ with Add ONs and configure a complete setup for the PMDG 737 Series! Don't worry the Snippet is available now so you can download and fly in just a couple of minutes!!

{% embed url="https://youtu.be/ksgmi13BBJo" %}
PMDG 737 TCA TQ + Addons
{% endembed %}

