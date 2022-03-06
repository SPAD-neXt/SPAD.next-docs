---
description: The 1-Command is used by the device to send configuration to SPAD.neXt.
---

# Serial: Configuration (1)

\
Request: `1,<SUBCOMMAND>[,<DATA>];`\
Reply: none

## SUBCOMMAND: `ADD`

The subcommand `ADD` informs SPAD.neXt about a data value the device will provide. This data can be used in events or expressions like any simulation data in the SPAD.neXt UI.

\
Format: `1,ADD,<CMDID>,<path>,<valuetype>,<access>,<name>[,description];`

| Parameter      | Description                                                                                                                                                                                                                                                                   | Limits                                             |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| `<CMDID>`      | the command id the device will use to send updates for that data                                                                                                                                                                                                              | >= 10                                              |
| \<path>        | <p> name of the data value. <br>To place it in a tree "//" can be used to separate the nodes. e.g. <code>buttons//button1</code> (<strong>note the escaped "/" !!</strong><br><strong></strong>If using CmdMessenger-Lib the escaping will be done automatically for you)</p> | name must not start with /                         |
| \<valuetype>   | type of the data (**S**igned/**U**nsigned)                                                                                                                                                                                                                                    | `S8 S16 S32 S64 U8 U16 U32 U64 FLT32 FLT64 ASCIIZ` |
| \<acces>       | **RO** for readonly, **RW** for readwrite                                                                                                                                                                                                                                     |                                                    |
| \<name>        | human readable name of the data for the UI                                                                                                                                                                                                                                    |                                                    |
| \<description> | optional description for the UI                                                                                                                                                                                                                                               |                                                    |

Within SPAD.neXt the data will be available in Serial->Devicename. \
Internally the Data is referenced as `<DeviceGUID>:<path>` \
e.g. `{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729}:buttons/button1`\
``\
`Example:`\
`1,ADD,11,buttons//button1,Activate Function,My cool description;`

## SUBCOMMAND: `SUBSCRIBE`

the subcommand `SUBSCRIBE` with subscribe the device to a data value from SPAD.neXt or the simulation\
Format: `1,SUBSCRIBE,<CMDID>,<path>[,<unit>[,<epsilon>]];`

|            |                                                                                                                                          |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `<CMDID>`  | commandid SPAD.neXt shall use to send data updates to the device                                                                         |
| \<path>    | internal name of the data value to subscribe to. E.g. `SIMCONNECT:AUTOPILOT HEADING LOCK DIR` `XPLANE:SIM/COCKPIT/AUTOPILOT/HEADING_MAG` |
| \<unit>    | desired unit, if not default (e.g. 'degrees','radians','Hz','kHz','MHz')                                                                 |
| \<epsilon> | minimum change that must happen before an update will be sent to the device. If it's omitted the default value for the data will be used |

Example\
1,SUBSCRIBE,12,SIMCONNECT:AUTOPILOT HEADING LOCK DIR\
``1,SUBSCRIBE,12,SIMCONNECT:AUTOPILOT HEADING LOCK DIR,radians\
1,SUBSCRIBE,12,XPLANE:sim//cockpit//autopilot//heading\_mag,,5

{% hint style="info" %}
You can get the internal name of a data value, by selecting it in the data browser and pressing `CTRL-C` or clicking on "book"-icon in the data monitor. It will be copied to the clipboard
{% endhint %}

## SUBCOMMAND: `UNSUBSCRIBE`

The subcommand `UNSUBSCRIBE` will unsubscribe from a previously subscribed data value\
Format: `1,UNSUBSCRIBE,<CMDID>;`

## SUBCOMMAND: `EMULATE`

The subcommand `EMULATE` will emulate an event from another device. (E.g. a dial turned on radio panel)\
Format: `1,EMULATE,<TARGET_DEVICE>,<TARGET_SWITCH>,<TARGET_EVENT>;`

`<TARGET_DEVICE>` is either the internal id (Format USB\_VID:USB\_PID:COUNTER ) or the serial number of the targeted device\
`<TARGET_SWITCH>` is the internal name of the switch/dial/led etc (e.g. FIP\_LEFTDIAL)\
`<TARGET_EVENT>` is name of the event to emulate (e.g. TUNER\_CLOCKWISE)

To get the TARGET\_SWITCH and TARGET\_EVENT you can program the event in the UI and then copy the complete event to the clipbaord, pasting to a texteditor.\
The TARGET\_SWITCH will be the "BOUNDTO" and the TARGET\_EVENT the "Trigger"

Alternatively you can get a list of all devices and events at Settings->Application->Expert->Available Remote Events

## SUBCOMMAND: XML

1,XML,\<sourcetype>,\<sourcename>\[,\<sourcedata>]

Instructs SPAD.neXt to get the device configuration as an XML from another source instead of configuring the device upon connect, to save device data space.

\<sourename> contains the name device xml the author/you has published using the SPAD.neXt device designer.\
\<sourcetype> defines where SPAD.neXt will look for the device xml

{% hint style="info" %}
the ALLOWLOCAL option (see OPTIONS) controls where SPAD will look for the xml\

{% endhint %}

### Sourcetype: SPAD

e.g.: 1,XML,SPAD,device.xml;

### Sourcetype: URL

\<sourcedata> contains the url of the xml to download. Only XML-is supported. If URL is not available/online no UI will be shown\
e.g.: 1,XML,URL,https://pastebin.com/zweWrQ

## SUBCOMMAND: IMAGE

1,IMAGE,\<sourcetype>,\<sourcename>\[,sourcedata]

Defines a custom image for the device UI.\
\[sourcedata] contains optional the **Base64**-encoded image-data

{% hint style="info" %}
the ALLOWLOCAL option (see OPTIONS) controls where SPAD will look for image\

{% endhint %}

{% hint style="warning" %}
#### Restrictions:

ImageSize must not exceed 640x480 pixel

Image should be transparent (e.g. PNG Format)
{% endhint %}

## DATA CHANNEL

SPAD.neXt will send data updates to the device and expect data using the given CMDID channel (see ADD/SUBSCRIBE) in the format: `<CMDID>,<DATA>;` `<DATA>` is always a float32 (Single precision floating point)
