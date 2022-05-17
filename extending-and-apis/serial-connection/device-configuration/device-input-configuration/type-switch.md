---
description: Define a stateful device switch
---

# Type = SWITCH

`0,INPUT,<Index>,<TAG>,SWITCH[,<Inherit>[,<OPTIONS>]]`

### \<Inherit>

The following inherits are available for switches to control the behaviour and available events:

|              |                  |   |
| ------------ | ---------------- | - |
| SPAD\_SWITCH | an ON/OFF switch |   |
|              |                  |   |
|              |                  |   |

If no inherit is present, the switch will not provide any standard events. The events have to be defined separately in the options

### \<Options>

For customizing the switch UI see (CUSTOM UI).

Default images used:

`IMG_ON`` `_`= svg/switch_1.svg`_

![](../../../../.gitbook/assets/switch\_1.svg)

`IMG_OFF`_`= svg/switch_0.svg`_

![](../../../../.gitbook/assets/switch\_0.svg)

For the SPAD.neXt standard UI of a switch the following options are supported:

|                 |                   |                                                                                                                      |
| --------------- | ----------------- | -------------------------------------------------------------------------------------------------------------------- |
| ROTATE=\<angle> | rotate switch-ui  | <p>ROTATE=90 (create left to right switch)<br>ROTATE=180 (create switch with OFF-Position is up instead of down)</p> |
|                 |                   |                                                                                                                      |
|                 |                   |                                                                                                                      |
