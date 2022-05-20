# Device STATESCAN-Phase

`0,SCANSTATE;`

this command tells the device that SPAD.neXt is now ready to receive the current state of stateful inputs (switches/rotaries/axis)

if the device does **not** support scanning of the states reply with `0,STATESCAN;`

if the device supports scanning of stateful inputs reply with

`0,STATESCAN,1;`

After the STATESCAN reply, issue any Device Input commands (8)\
if any events will be executed in statescan phase is defined in the SPD.neXt profile

and finally send a&#x20;

`0,STATESCAN,2;`

to notify SPAD.neXt that the state-scanning has completed
