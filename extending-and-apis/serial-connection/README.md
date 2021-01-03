# Serial Interface

SPAD.neXt can communicate with external devices like e.g. Arduino/Teensy via serial communication.

For a SPAD.neXt compatible Arduino library import CmdMessenger \(4.0\) into the Arduino IDE \(recommended\) or clone the github repository at [https://github.com/thijse/Arduino-CmdMessenger](https://github.com/thijse/Arduino-CmdMessenger)

Request and Reply on both sides will always follow this format:

`<COMMANDID>,<PARAM-1>,...,<PARAM-n>;`

If ",","/" or ";" are used within the parameters, they have to be escaped by a leading "/". E.g.  
`15,Hello/, from Arduino;`

### Defined Command-ID's:

`0` Command Channel SPAD.neXt -&gt; Device  
`1` Command Channel Device -&gt; SPAD.neXt  
`2` Event Channel SPAD.neXt -&gt; Device  
`3` Debug Channel  
`4` Simulation Command Channel Device -&gt; Simulation

`5 .. 9` Reserved for future use  
`10..49` Data Update Channels \(both directions\)

## Commands

* [Command: 0](command-0.md)
* [Command: 1](https://github.com/c0nnex/SPAD.next-docs/tree/3d7ff617b724c2c2c2a1802509be5ba220982c08/extending-and-apis/serial-interface/command-1.md)
* [Command: 2](https://github.com/c0nnex/SPAD.next-docs/tree/3d7ff617b724c2c2c2a1802509be5ba220982c08/extending-and-apis/serial-interface/command-2.md)
* [Data Updates](https://github.com/c0nnex/SPAD.next-docs/tree/3d7ff617b724c2c2c2a1802509be5ba220982c08/extending-and-apis/serial-interface/command-data-updates.md)



