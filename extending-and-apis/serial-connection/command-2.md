# Serial: Events (CMDID 2)

The 2-Command is used by SPAD.neXt to inform the device about events. There are some events that the device might ignore, and some that it should react to.

`2,START;` -> The device can send data updates now , if any\
`2,STOP;`-> The device should stop sending data updates\
`2,AIRCRAFTCHANGED,<new name>;` -> the loaded aircraft changed\
`2,PROFILECHANGED,<new profile name>;` -> the loaded SPAD.neXt profile changed\
`2,CONNECT,<simulation name>;` -> a simulation connected to SPAD.neXt\
`2,DISCONNECT,<simulation name>;` -> a simulation disconnected from SPAD.neXt

2,PAGE,\<GUID>,\<completed>,\<name>; -> Switch to page&#x20;

2,VIRTUALPOWER,\<onoff>\
