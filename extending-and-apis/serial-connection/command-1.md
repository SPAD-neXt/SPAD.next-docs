# Command: 1

The 1-Command is used by the device to send commands to SPAD.neXt.  
Request: `1,<SUBCOMMAND>[,<DATA>];`  
Reply: none

## SUBCOMMAND: `ADD`

The subcommand `ADD` informs SPAD.neXt about a data value that the device will provide, so it can be bound to events.  
Format: `1,ADD,<CMDID>,<path>,<valuetype>,<access>,<name>[,description];`

`<CMDID>` is the command id the device will use to send updates for that data. \(9 &lt; ID &lt; 50\)  
`<path>` the internal name of the data value. To place it in a tree "//" can be used to separate the nodes. e.g. `buttons//button1` \(**note the escaped "/" !!** If using CmdMessenger-Lib the escaping will be done automatically for you\) The path must not contain ":".  
`<valuetype>` the type of the data \(Signed/Unsigned\) one of `S8,S16,S32,S64,U8,U16,U32,U64,FLT32,FLT64,ASCIIZ`  
`<access>` RO for readonly, RW for readwrite  
`<name>` human readable name of the data for the UI  
`<description>` optional description for the UI

Within SPAD.neXt the data will be available in Serial-&gt;Devicename. Internally the Data is referenced as `SERIAL:<DeviceGUID>/<path>` e.g. `SERIAL:{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729}/buttons/button1`

## SUBCOMMAND: `SUBSCRIBE`

the subcommand `SUBSCRIBE` with subscribe the device to a data value from SPAD.neXt.  
Format: `1,SUBSCRIBE,<CMDID>,<path>[,<unit>[,<epsilon>]];`

`<CMDID>` is the commandid SPAD.neXt shall use to send data updates to the device  
`<path>` is the internal name of the data value to subscribe to. E.g. `SIMCONNECT:AUTOPILOT HEADING LOCK DIR` `XPLANE:SIM/COCKPIT/AUTOPILOT/HEADING_MAG`  
`<unit>` is the desired unit, if not default \(e.g. 'degrees','radians','Hz','kHz','MHz'\)  
`<epsilon>` is the minimum change that must happen before an update will be sent to the device. If it's omitted the default value for the data will be used

## SUBCOMMAND: `UNSUBSCRIBE`

The subcommand `UNSUBSCRIBE` will unsubscribe from a previously subscribed data value  
Format: `1,UNSUBSCRIBE,<CMDID>;`

## SUBCOMMAND: `EMULATE`

The subcommand `EMULATE` will emulate an event from another device. \(E.g. a dial turned on radio panel\)  
Format: `1,EMULATE,<TARGET_DEVICE>,<TARGET_SWITCH>,<TARGET_EVENT>;`

`<TARGET_DEVICE>` is either the internal id \(Format USB\_VID:USB\_PID:COUNTER \) or the serial number of the targeted device  
`<TARGET_SWITCH>` is the internal name of the switch/dial/led etc \(e.g. FIP\_LEFTDIAL\)  
`<TARGET_EVENT>` is name of the event to emulate \(e.g. TUNER\_CLOCKWISE\)

To get the TARGET\_SWITCH and TARGET\_EVENT you can program the event in the UI and then copy the complete event to the clipbaord, pasting to a texteditor.  
The TARGET\_SWITCH will be the "BOUNDTO" and the TARGET\_EVENT the "Trigger"

Alternatively you can get a list of all devices and events at Settings-&gt;Application-&gt;Expert-&gt;Available Remote Events

## DATA CHANNEL

SPAD.neXt will send data updates to the device and expect data using the given CMDID channel \(see ADD/SUBSCRIBE\) in the format: `<CMDID>,<DATA>;` `<DATA>` is always a float32 \(Single precision floating point\)

