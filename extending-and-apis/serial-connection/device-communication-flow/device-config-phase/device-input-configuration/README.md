---
description: Define a device input (Device -> SPAD)
---

# Device INPUT configuration

`0,INPUT,<Index>,<Tag>,<Type>[,<Inherit>[,<OPTIONS>]];`

All input definition follow the same definition.

\<Index> being a numeric index that is used for sending input updates to SPAD.neXt

\<Tag> being the internal name of the input. This will be used for identifying actions bound to this input

\<type> being the internal type of the input

\<inherit> the default events to include in this input. if it's not provided the definition must provide the custom events.

\<options> optional options to alter the behavior/ui of an input

### Options supported for all Inputs and Outputs

|                 |                                                                                             |   |
| --------------- | ------------------------------------------------------------------------------------------- | - |
| NO\_LABEL=1     | Disable the state-value label above the input in SPAD.neXt standard UI                      |   |
| ORDER=\<number> | Defines the ordering in SPAD UI. Default 0 = All elements are shown in order as they arrive |   |
|                 |                                                                                             |   |

### Sending INPUT updates

For all inputs the devices uses the channel 8 to send updates to SPAd.neXt:

`8,<index>,<value>;`

\<index> being the index given in the input configuration

\<value> being the new value
