# Serial Interface

SPAD.neXt can communicate with external devices like e.g. Arduino/Teensy via a very simple line based communication.

Request and reply on both sides will follow this format:

`<CHANNELID>,<PARAM1>,...,<PARAMn>;`

{% hint style="danger" %}
If `, / ;` are used within the parameters, they have to be escaped by a leading /. \
E.g.\
`15,Hello/, from Arduino;`
{% endhint %}

{% hint style="info" %}
For a SPAD.neXt compatible Arduino library import CmdMessenger (4.0) into the Arduino IDE (recommended) or clone the github repository at [https://github.com/thijse/Arduino-CmdMessenger](https://github.com/thijse/Arduino-CmdMessenger)

There is also a customized version available at the SPAD.neXt GitHub (TODO LINK) which includes SPAD.neXt specific functions to make device programming more easy.
{% endhint %}

{% hint style="info" %}
The same protocol can be used to communicate with SPAD.neXt e.g. via a Websocket (TODO WEBSOCKET) and procide e.g. a custom webinterfaced device
{% endhint %}

## Channel-ID's

| ChannelID | Purpose                   | Direction        |
| --------- | ------------------------- | ---------------- |
| 0         | General Commands          | SPAD <--> Device |
| 1         | Data Commands             | Device -> SPAD   |
| 2         | SPAD.neXt Events          | SPAD -> Device   |
| 3         | Debug                     | Device -> SPAD   |
| 4         | Simulation Event          | Device -> SPAD   |
| 5         | Data Channel              | SPAD -> Device   |
| 6         | Device LED updates        | SPAD -> Device   |
| 7         | Device Display updates    | SPAD -> Device   |
| 8         | Device Input              | Device -> SPAD   |
| 9         | (reserved for future use) |                  |
| 10 .. 49  | Dedicated Data Channels   | SPAD <-> Device  |

{% hint style="info" %}
By default cmdMessenger is limited to a max of 50 channels to preserve device memory. You can change that by altering the line\
`#define MAXCALLBACKS 50`\
in cmdMessenger.h, however this is **not** recommended.
{% endhint %}

## Communication Flow

Initialization Phase

| SPAD.neXt sends              | Device sends              | Comment                                                                   |
| ---------------------------- | ------------------------- | ------------------------------------------------------------------------- |
| 0,INIT...                    |                           |                                                                           |
|                              | 0,SPAD,...                |                                                                           |
| 0,CONFIG\[,Parameters]       |                           |                                                                           |
|                              | 0,INPUT/OUTPUT/OPTIONS... | Only if device needs to configure anything                                |
|                              | 0,CONFIG;                 | <p>Device Setup completed<br><strong>Needs to be sent always</strong></p> |
| (any queued events and data) |                           |                                                                           |
| 0,START;                     |                           |                                                                           |

