---
description: Genral Command ( SPAD.neXt <--> Device)
---

# Serial: General Command (0)

The Command 0 is used by SPAD.neXt to send commands to the Device. The format is `0,<SUBCOMMAND>,<DATA>...;`

## SUBCOMMAND: INIT



## SUBCOMMAND: CONFIG

The subcommand 'CONFIG' is sent by SPAD.neXt to tell the device that it can now send it's configuration data to SPAD.neXt using the configuration command (1) \
\
The device will now send configration commands (1) to SPAD.neXt for initial configuration. \
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
