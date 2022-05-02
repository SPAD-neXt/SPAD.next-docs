# Serial Interface

SPAD.neXt can communicate with external devices like e.g. Arduino/Teensy via a very simple line based communication.



Request and reply on both sides will follow this format:

`<COMMANDID>,<PARAM1>,...,<PARAMn>;`

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
The same protocol can be used to communicate with SPAD.neXt e.g. via a Websocket (TODO WEBSOCKET)
{% endhint %}

### Pre-Defined Command-ID's:

| CommandID | Purpose                 | Direction        |
| --------- | ----------------------- | ---------------- |
| 0         | General Command         | SPAD <--> Device |
| 1         | Configuration           | Device -> SPAD   |
| 2         | Events                  | SPAD -> Device   |
| 3         | Debug                   | Device -> SPAD   |
| 4         | Simulation Event        | Device -> SPAD   |
| 5         | Simulation Data         | SPAD -> Device   |
| 6         | Device LED updates      | SPAD -> Device   |
| 7         | Device Display updates  | SPAD -> Device   |
| 8         | Device Input            | Device -> SPAD   |
| 9         | (reserved)              |                  |
| 10 .. 49  | Dedicated Data Commands | SPAD <-> Device  |

## Communication Flow

Initialization Phase

| SPAD.neXt sends              | Device sends              | Comment                                                                   |
| ---------------------------- | ------------------------- | ------------------------------------------------------------------------- |
| 0,INIT...                    |                           |                                                                           |
|                              | 0,SPAD,...                |                                                                           |
| 0,CONFIG\[,Parameters]       |                           |                                                                           |
|                              | 1,INPUT/OUTPUT/OPTIONS... | Only if device needs to configure anything                                |
|                              | 0,CONFIG;                 | <p>Device Setup completed<br><strong>Needs to be sent always</strong></p> |
| (any queued events and data) |                           |                                                                           |
| 0,START;                     |                           |                                                                           |

## Commands

* [Command: 0](command-0.md)
* [Command: 1](command-1/)
* [Command: 2](command-2.md)
* [Data Updates](command-data-updates.md)

