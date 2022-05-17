---
description: Define a stateful rotary switch
---

# Device input ROTARY

`0,INPUT,<index>,<tag>,ROTARY,<inherit>,<options>;`

For a stateful rotary the states have to be defined in the options.

In SPAD.neXt standard UI the rotary is visualized as following (uivalue = 0):

`IMG=svg/rotary.svg`

![](../../../../../.gitbook/assets/rotary.svg)

### Available Inherits

|                      |                                                      |                            |
| -------------------- | ---------------------------------------------------- | -------------------------- |
| `SPAD_ENCODER_NOACC` | provide additional Clockwise/Counterclockwise events | Acceleration not supported |
| `<EMPTY/OMITTED>`    | No tuner events                                      |                            |
|                      |                                                      |                            |

### Options

|                                      |                                                                                                         |                                      |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| POS\_NAMES=statename1.statename2.... | a list of the statenames of the rotary separated by "#" (hash)                                          | POS\_NAMES=OFF#LEFT#RIGHT#BOTH#START |
| POS\_VALUES=val1.val2.val3....       | a list of the statevalues the device will use in the input events of the rotary separated by "#" (hash) | POS\_VALUES=0#1#2#3#4                |
| POS\_UIVALUES=val1.val2.val3....     | the rotation ui values for the states (real rotation = 15\*value degrees)                               | POS\_UIVALUES=-3#0#3#6#9             |
|                                      |                                                                                                         |                                      |

### Sending rotary input updates

`8,<index>,<statevalue>;`

e.g to tell SPAD.neXt that the rotary (index 5 tag E\_MAGNETO) has been changed to BOTH-Position the device will send a&#x20;

`8,5,3;`

command. \
SPAD.neXt will execute the events

`E_MAGENTO.BOTH`

`E_MAGNETO.TUNER_CLOCKWISE` if previous position was RIGHT and encoder inherit was present

and rotate the UI-representation by 6 \* 15  = 90 degrees

