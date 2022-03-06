# Serial Interface

SPAD.neXt can communicate with external devices like e.g. Arduino/Teensy via a very simple serial communication.



Request and Reply on both sides will follow this format:

`<COMMANDID>,<PARAM1>,...,<PARAMn>;`

{% hint style="danger" %}
If `, / ;` are used within the parameters, they have to be escaped by a leading /. \
E.g.\
`15,Hello/, from Arduino;`
{% endhint %}

{% hint style="info" %}
For a SPAD.neXt compatible Arduino library import CmdMessenger (4.0) into the Arduino IDE (recommended) or clone the github repository at [https://github.com/thijse/Arduino-CmdMessenger](https://github.com/thijse/Arduino-CmdMessenger)
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
| 6         | Device LED              | SPAD -> Device   |
| 7         | Device Display          | SPAD -> Device   |
| 8         | Device Input            | Device -> SPAD   |
| 9         | (reserved)              |                  |
| 10 .. 49  | Dedicated Data Commands | SPAD <-> Device  |

## Commands

* [Command: 0](command-0.md)
* [Command: 1](command-1.md)
* [Command: 2](command-2.md)
* [Data Updates](command-data-updates.md)

