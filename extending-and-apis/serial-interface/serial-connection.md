SPAD.neXt can communicate with external devices like e.g. Arduino/Teensy via serial communication.

For a SPAD.neXt compatible Arduino library import CmdMessenger (4.0) into the Arduino IDE (recommended) or clone the github repository at https://github.com/thijse/Arduino-CmdMessenger

Request and Reply on both sides will always follow this format:

`<COMMANDID>,<PARAM-1>,...,<PARAM-n>;`

If ",","/" or ";" are used within the parameters, they have to be escaped by a leading "/". E.g.   
`15,Hello/, from Arduino;`


### Defined Command-ID's:  
`0` Command Channel SPAD.neXt -> Device  
`1` Command Channel Device -> SPAD.neXt  
`2` Event Channel SPAD.neXt -> Device  
`3` Debug Channel  
`4` Simulation Command Channel Device -> Simulation

`5 .. 9` Reserved for future use  
`10..49` Data Update Channels (both directions)

# Commands
* [Command: 0](command-0.md)
* [Command: 1](command-1.md)
* [Command: 2](command-2.md)
* [Data Updates](command-data-updates.md)




