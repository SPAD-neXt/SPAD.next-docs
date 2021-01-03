# Command: 2

The 2-Command is used by SPAD.neXt to inform the device about events. There are some events that the device might ignore, and some that it should react to.

`2,START;` -&gt; The device can send data updates now , if any  
`2,STOP;`-&gt; The device should stop sending data updates  
`2,AIRCRAFTCHANGED,<new name>;` -&gt; the loaded aircraft changed  
`2,PROFILECHANGED,<new profile name>;` -&gt; the loaded SPAD.neXt profile changed  
`2,CONNECT,<simulation name>;` -&gt; a simulation connected to SPAD.neXt  
`2,DISCONNECT,<simulation name>;` -&gt; a simulation disconnected from SPAD.neXt

