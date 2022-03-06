---
description: Genral Command ( SPAD.neXt <--> Device)
---

# Serial: General Command (0)

The Command 0 is used by SPAD.neXt to send commands to the Device. The format is `0,<SUBCOMMAND>,<DATA>...;`

## SUBCOMMAND: INIT

When starting SPAD.neXt will send an INIT Request to all serial devices configured and expects them to respond within 5 seconds, else the device will be marked as offline/unavailable.

Request:\
`0,INIT,<SerialVersion>,<AppVersion>,<AuthToken>`

`Parameters`\
``

| \<SerialVersion> | <p>Version of the serial protocol supported <br>2 means SPAD.neXt is support version 1 and version 2<br>The current version is 2</p>                                                                                                                                   |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<AppVersion>    | SPAD.neXt version (e.g. 0.9.12.0 )                                                                                                                                                                                                                                     |
| \<AuthToken>     | A unique ID identifying the SPAD.neXt instance used as authentication tag in AuthenticationCipher (See [http://rweather.github.io/arduinolibs/classAuthenticatedCipher.html](http://rweather.github.io/arduinolibs/classAuthenticatedCipher.html#details) for details) |

Reply:\
`0,SPAD,<GUID>,<NAME>,<SerialVersion>,<DeviceVersion>[,<opt1>,...,<optN>;`

| `<GUID>`          |  Unique Identifier identifying the device. It should follow the GUID-Registryformat e.g. "{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729}". To create a GUID you can use this site: [https://www.guidgenerator.com/online-guid-generator.aspx](https://www.guidgenerator.com/online-guid-generator.aspx) (enable braces and hyphens) |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<NAME>           | the human readable name of the device. This will be used throughout the SPAD.neXt UI for everything related to that device                                                                                                                                                                                                  |
| \<ServialVersion> | Serialversion the device is supporting                                                                                                                                                                                                                                                                                      |
| \<DeviceVersion>  | Version of the device (Major.Minor\[.Build.Patch])                                                                                                                                                                                                                                                                          |
| \<opt1>...\<optN> | device options (see TODO OPTIONS)                                                                                                                                                                                                                                                                                           |

\
**Example**\
Request: `0,INIT,2,0.9.10.0,73993732632;`\
Reply (go ahead): `0,SPAD,{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729},Altimeter Display,2,1.0;`\
Reply (error): `0,ERROR;` (e.g. version not supported)

## SUBCOMMAND: CONFIG

The subcommand 'CONFIG' is sent by SPAD.neXt to tell the device that it can now send it's configuration data to SPAD.neXt using the configuration command (1) \
\
The device will now send configration commands (1) to SPAD.neXt for initial datas. \
When it's done the device sends a '0,CONFIG;' response.

Request: `0,CONFIG;`\
Reply: (any '1'-Commands and then) `0,CONFIG;`

{% hint style="warning" %}
The device will not show up in SPAD.neXt UI before configuration is completed
{% endhint %}

## SUBCOMMAND: PING

Every 10 Seconds SPAD.neXt will send a PING to the device and expects a PONG in response containing the received TICKET as payload.&#x20;

{% hint style="info" %}
If no PONG is received for longer than 30 seconds, SPAD.neXt assumes the device is offline.
{% endhint %}

\
Request: `0,PING,<TICKET>;`\
Reply: `0,PONG,<TICKET>;`

## SUBCOMMAND: END

When SPAD.neXt exits it will send an `0,END;` command to the device, so the device knows SPAD.neXt is exiting. \


{% hint style="danger" %}
There is no guarantee that this command is sent, and SPAD.neXt will not wait for a reply and close the comunication immediately
{% endhint %}
