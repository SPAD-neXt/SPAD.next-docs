# Device Simulation Events

The channel 4 is used by the device to send commands/events to the connected simulation.\
Request: `4,<SIMNAME:EVENTNAME>[,<Value Default=0>[,<Value2>];`\
Reply: none

`<SIMNAME:EVENTNAME>` is the event to send to the simulation. e.g. SIMCONNECT:FLAPS\_UP. The "SIMNAME:" part can be omitted, then SIMCONNECT: is assumed.\
`<Value>` can be a int value to send with the command&#x20;

SIMCONNECT: Events/Commands will be automatically transcribed to the according connected Simulation (e.g. XPLANE)

MSFS / H:Events: e.g.    MSFS:AS1000\_MFD\_DIRECTTO
