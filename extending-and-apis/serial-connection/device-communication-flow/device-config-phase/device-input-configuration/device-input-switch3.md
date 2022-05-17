---
description: Define a stateful 3-Position (On1-Mid2-On0) switch
---

# Device input SWITCH3

`0,INPUT,<index>,<tag>,SWITCH3[,<inherit>[,<options]];`

### Mandatory options

|                              |                                 |                        |
| ---------------------------- | ------------------------------- | ---------------------- |
| POS\_NAMES=name0#name1#name2 | Event names of the 0/1/2 states | POS\_NAMES=OFF#UP#DOWN |
|                              |                                 |                        |
|                              |                                 |                        |

UI customization

`IMG_0= svg/switch_0.svg`

`IMG_1= svg/switch_1.svg`

`IMG_2= svg/switch_2.svg`

### Sending switch3 input updates

`8,<index>,<statevalue>;`

statevalue = 0 switched to ON0 position

statevalue = 1 switched to ON1 Position

statevalue = 2 switched to MID2 Position
