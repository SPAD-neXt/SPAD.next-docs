---
description: Define a device input (Device -> SPAD)
---

# Device INPUT configuration

0,INPUT,\<Index>,\<Tag>,\<Type>\[,\<Inherit>\[,\<OPTIONS>]];

All input definition follow the same definition.

\<Index> being a numeric index that is used for sending input updates to SPAD.neXt

\<Tag> being the internal name of the input. This will be used for identifying actions bound to this input

\<type> being the internal type of the input

\<inherit> the default events to include in this input. if it's not provided the definition must provide the custom events.

\<options> optional options to alter the behavior/ui of an input

Options supported for all Inputs

|             |                                                                        |   |
| ----------- | ---------------------------------------------------------------------- | - |
| NO\_LABEL=1 | Disable the state-value label above the input in SPAD.neXt standard UI |   |
|             |                                                                        |   |
|             |                                                                        |   |

