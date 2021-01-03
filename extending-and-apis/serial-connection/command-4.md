# Command: 4

The 4-Command is used by the device to send commands/events to the connected simulation.  
Request: `4,<SIMNAME:EVENTNAME>[,<Value Default=0>];`  
Reply: none

`<SIMNAME:EVENTNAME>` is the event to send to the simulation. e.g. SIMCONNECT:FLAPS\_UP. The "SIMANME:" part can be omitted, then SIMCONNECT: is assumed.  
`<Value>` can be a int value to send with the command if any

SIMCONNECT: Events/Commands will be automatically transcribed to the according connected Simulation \(e.g. XPLANE\)

