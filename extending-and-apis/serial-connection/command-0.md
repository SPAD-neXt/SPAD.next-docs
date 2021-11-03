# Command: 0

The Command 0 is used by SPAD.neXt to send commands to the Device. The format is `0,<SUBCOMMAND>,<DATA>;`

## SUBCOMMAND: INIT

When starting SPAD.neXt will send an INIT Request to all serial devices configured and expects them to respond within 5 seconds, else the device will be marked as offline/unavailable.

Request:\
`0,INIT,<Version>;` (\ currently = 1)

Reply:\
`0,SPAD,<GUID>,<NAME>;`\
\<GUID> is a Unique Identifier identifying the device. It should follow the GUID-Registryformat e.g. "{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729}". To create a GUID you can use this site: [https://www.guidgenerator.com/online-guid-generator.aspx](https://www.guidgenerator.com/online-guid-generator.aspx) (enable braces and hyphens)\
\<NAME> is the human readable name of the device. This will be used throughout the SPAD.neXt UI for everything related to that device.

**Example**\
Request: `0,INIT,1;`\
Reply (go ahead): `0,SPAD,{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729},Altimeter Display;`\
Reply (error): `0,ERROR;` (e.g. version not supported)

## SUBCOMMAND: CONFIG

The subcommand 'CONFIG' is sent by SPAD.neXt to tell the device that it can now send it's data requests and data announcements to SPAD.neXt. The device **must not** send any data updates before it is told to do so!\
The device will now send Command "1" (See below) packets to SPAD.neXt for initial datas. When it's done the device sends a '0,CONFIG;' response.

Request: `0,CONFIG;`\
Reply: (any '1'-Commands and then) `0,CONFIG;`

## SUBCOMMAND: PING

Every 10 Seconds SPAD.neXt will send a PING to the device and expects a PONG back. If no PONG is received for longer than 30 seconds, SPAD.neXt assumes the device is offline.

Request: `0,PING,<TICKET>;`\
Reply: `0,PONG,<TICKET>;`

## SUBCOMMAND: END

When SPAD.neXt exits it will send an `0,END;` command to the device, so the device knows SPAD.neXt is exiting. There is no guarantee that this command is sent, and SPAD.neXt will not wait for a reply.
