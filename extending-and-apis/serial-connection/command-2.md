---
description: SPAD.neXt raises internal events on Channel 2
---

# Device SPAD.neXt Events (2)

The channel 2 is used by SPAD.neXt to inform the device about events. There are some events that the device might ignore, and some that it should react to.

`2,START;` -> The device can send data updates now , if any\
`2,STOP;`-> The device should stop sending data updates\
`2,AIRCRAFTCHANGED,<new name>;` -> the loaded aircraft changed

`2,PROFILECHANGING,<new pofile name>;` -> the profile is about to change\
`2,PROFILECHANGED,<new profile name>;` -> the loaded SPAD.neXt profile changed and is active\
`2,CONNECT,<simulation name>;` -> a simulation connected to SPAD.neXt\
`2,DISCONNECT,<simulation name>;` -> a simulation disconnected from SPAD.neXt

2,PAGE,\<GUID>,\<completed>,\<name>; -> Switch to page&#x20;

2,VIRTUALPOWER,\<onoff>

2,LABEL,\<index>,\<newlabel>;

2,PROVIDER,\<name>,\<status>; -> The status of a provider has changed



When the profile is switched in SPAD.neXt the following events will be sent to the device:

1. PROFILECHANGING
2. PAGE (completed = 0)
3. PAGE (completed = 1)
4. PROFILECHANGED

(2 and 3 only if device supported pages)\
