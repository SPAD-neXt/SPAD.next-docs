---
description: The 1-Command is used by the device to send commands to SPAD.neXt.
---

# Device commands

\
Request: `1,<SUBCOMMAND>,...;`\
Reply: none or 2,ERROR

## Provide Data to SPAD.neXt

The subcommand `ADD` informs SPAD.neXt about a data value the device will provide. This data can be used in events or expressions like any simulation data in the SPAD.neXt UI.

\
&#x20;`1,ADD,<CHANNELID>,<path>,<valuetype>,<access>,<name>[,description][,options];`

| Parameter      | Description                                                                                                                                                                                                                                                                   | Limits                                             |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| `<CHANNELID>`  | the Channel the device/SPAD.neXt will use to send updates for that data                                                                                                                                                                                                       | >= 10                                              |
| \<path>        | <p> name of the data value. <br>To place it in a tree "//" can be used to separate the nodes. e.g. <code>buttons//button1</code> (<strong>note the escaped "/" !!</strong><br><strong></strong>If using CmdMessenger-Lib the escaping will be done automatically for you)</p> | name must not start with /                         |
| \<valuetype>   | type of the data (**S**igned/**U**nsigned)                                                                                                                                                                                                                                    | `S8 S16 S32 S64 U8 U16 U32 U64 FLT32 FLT64 ASCIIZ` |
| \<acces>       | **RO** for readonly, **RW** for readwrite                                                                                                                                                                                                                                     |                                                    |
| \<name>        | human readable name of the data for the UI                                                                                                                                                                                                                                    |                                                    |
| \<description> | optional description for the UI                                                                                                                                                                                                                                               |                                                    |

Supported options

|         |      |                                                                 |
| ------- | ---- | --------------------------------------------------------------- |
| ASLOCAL | 0\|1 | Create a LOCAL variable instead of a persistent DEVICE variable |

Within SPAD.neXt the data will be available in Device->Devicename. \
Internally the Data is referenced as `DEVICE:{DeviceId}/<path>` \
e.g.  DEVICE:`A8AA15C5-7BB6-4AC6-A558-A88CAFB78729/buttons/button1`

**Device Data is only available within the profile of the device.**&#x20;

SPAD.neXt will send data updates to the device and expect data using the given CHANNELID channel using the 5-Channel: 5,`<CHANNELID>,<value>;` \
``\
``Examples:\
`1,ADD,11,pages//activepage,U8,RW,Active device page,My cool description;`

creates a variable `DEVICE:GUID/pages/activepage` available only within the deviceperofile of the device. outside of the deviceprofile this variable will always have the value 0

`1,ADD,11,pages//activepage,U8,RW,Active device page,,ASLOCAL=1;`

creates a variable `LOCAL:VID/PID/SERIAL/pages/activepage` available to all deviceprofiles within SPAD.neXt

{% hint style="danger" %}
DEVICE variables are persitent per connected devices and the values will be loaded and saved from/to the profile. &#x20;

LOCAL variables will not be saved and default to 0&#x20;
{% endhint %}



## Subscribe to a data&#x20;

the subcommand `SUBSCRIBE` with subscribe the device to a data value from SPAD.neXt or the simulation\


`1,SUBSCRIBE,<index>,<path>[,<unit>[,<epsilon>]];`

|            |                                                                                                                                          |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `<index>`  | the index associated with the data                                                                                                       |
| \<path>    | internal name of the data value to subscribe to. E.g. `SIMCONNECT:AUTOPILOT HEADING LOCK DIR` `XPLANE:SIM/COCKPIT/AUTOPILOT/HEADING_MAG` |
| \<unit>    | desired unit, if not default (e.g. 'degrees','radians','Hz','kHz','MHz')                                                                 |
| \<epsilon> | minimum change that must happen before an update will be sent to the device. If it's omitted the default value for the data will be used |



{% hint style="success" %}
SPAD.neXt will send the subscribed data on the 5-Channel in the format

`5,<index>,<value>;`


{% endhint %}

Example\
1,SUBSCRIBE,12,SIMCONNECT:AUTOPILOT HEADING LOCK DIR\
``1,SUBSCRIBE,12,SIMCONNECT:AUTOPILOT HEADING LOCK DIR,radians\
1,SUBSCRIBE,12,XPLANE:sim//cockpit//autopilot//heading\_mag,,5

{% hint style="info" %}
You can get the internal name of a data value, by selecting it in the data browser and pressing `CTRL-C` or clicking on "book"-icon in the data monitor. It will be copied to the clipboard
{% endhint %}

## Unsubscribe from a data

The subcommand `UNSUBSCRIBE` will unsubscribe from a previously subscribed data value\
Syntax: `1,UNSUBSCRIBE,<index>;`

## Emulate an event on a diffrent device

The subcommand `EMULATE` will emulate an event from another device. (E.g. a dial turned on radio panel)\


`1,EMULATE,<TARGET_DEVICE>,<TARGET_SWITCH>,<TARGET_EVENT>;`

`<TARGET_DEVICE>` is either the internal id `VID:PID:COUNTER` or `VID:PID:SERIAL`\
`<TARGET_SWITCH>` is the internal name of the switch/dial/led etc (e.g. FIP\_LEFTDIAL)\
`<TARGET_EVENT>` is name of the event to emulate (e.g. TUNER\_CLOCKWISE)

To get the TARGET\_SWITCH and TARGET\_EVENT you can program the event in the UI and then copy the complete event to the clipboard, pasting to a texteditor.\
The TARGET\_SWITCH will be the "BOUNDTO" and the TARGET\_EVENT the "Trigger"

Alternatively you can get a list of all devices and events at Settings->Application->Expert->Available Remote Events

## Update the labeltext of an input/output or label

`1,LABEL,<index>,<newlabel>;`

Updates the labeltext of a input/led (DYNLABEL=1 !) or a label pseudo input
