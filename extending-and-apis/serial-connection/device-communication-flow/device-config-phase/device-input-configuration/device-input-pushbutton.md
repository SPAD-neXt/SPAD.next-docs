---
description: Stateless push button
---

# Device input PUSHBUTTON

Pushbutton with Press / Press short / Press long / Relase events

`0,INPUT,<Index>,<TAG>,PUSHBUTTON[,<Inherit>[,<OPTIONS>]];`

Simple Pushbutton with Press and  Relase events

`0,INPUT,<Index>,<TAG>,PUSHBUTTON_NOMODE[,<Inherit>[,<OPTIONS>]];`

### Available inherits

|                          |                                                                                           |   |
| ------------------------ | ----------------------------------------------------------------------------------------- | - |
| SPAD\_PUSHBUTTON         | a standard SPAD.neXt push button with `PRESS / PRESS_SHORT / PRESS_LONG / RELEASE` events |   |
| `SPAD_PUSHBUTTON_NOMODE` | a simple pushbutton with PRESS / RELEASE Events                                           |   |
|                          |                                                                                           |   |

### Available options

|        |                                                                    |   |
| ------ | ------------------------------------------------------------------ | - |
| HELD=1 | Enables "Held-mode" support for HELD event while button is pressed |   |
|        |                                                                    |   |
|        |                                                                    |   |

### Sending button input updates

`8,<index>,<statevalue>;`

statevalue = 0 button released

statevalue = 1 button pressed
