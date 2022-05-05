---
description: General Command ( SPAD.neXt <--> Device) on Channel 0
---

# Device General Commands

## STATESCAN

Syntax: `0,STATESCAN;`

this command tells the device that SPAD.neXt is now ready to receive the current state of stateful inputs (switches/rotaries/axis)

if the device does **not** support scanning of the states reply with `0,STATESCAN;`

if the device supports scanning of stateful inputs reply with

`0,STATESCAN,1[,<Behavior>];`

`BEHAVIOR`

`0` instructs SPAD.neXt just to update the UI and do not execute any events

`1` instructs SPAD.neXt to update the UI and execute all events associated with the states

After the STATESCAN reply, issue any Device Input commands (8) ``&#x20;

and finally send a&#x20;

`0,STATESCAN,2;`

to notify SPAD.neXt that the state-scanning has completed

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
