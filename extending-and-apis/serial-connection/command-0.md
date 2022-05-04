---
description: Genral Command ( SPAD.neXt <--> Device)
---

# General Commands

## &#x20;PING

Every 10 seconds SPAD.neXt will send a PING to the device and expects a PONG in response containing the received TICKET as payload.&#x20;

{% hint style="info" %}
If no PONG is received for longer than 30 seconds, SPAD.neXt assumes the device is offline.
{% endhint %}

\
Request: `0,PING,<TICKET>;`\
Reply: `0,PONG,<TICKET>;`

## &#x20;END

When SPAD.neXt exits it will send an `0,END;` command to the device, so the device knows SPAD.neXt is exiting. \


{% hint style="danger" %}
There is no guarantee that this command is sent, and SPAD.neXt will not wait for a reply and close the comunication immediately
{% endhint %}

Request: `0,END;`\
Reply: none
