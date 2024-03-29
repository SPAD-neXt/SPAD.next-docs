---
description: Set device specific options
---

# Device options

Syntax: `0,OPTION,<Key>=<Value>[,<Key2>=<Value2>,...];`

## Simple Device options

Syntax: `Optionkey=Value`

| Key                  | ValueType  | Description                                                                                                                |
| -------------------- | ---------- | -------------------------------------------------------------------------------------------------------------------------- |
| OUT\_COOLDOWN        | number     | Time in milliseconds SPAD will wait after each sent command/data to give the device time to process it (Default: 25ms)     |
| PROFILE\_RO          | 0\|1       | If the device profile cannot be edited by the user                                                                         |
| PROFILE\_ENC         | 0\|1       | the profile part of the device will be encrypted                                                                           |
| ISGENERIC            | 0\|1       | Device will not provide any UI, SPAD wil generate a generic UI                                                             |
| PAGESUPPORT          | 0\|1       | If the device supports profile pages                                                                                       |
| NO\_DISPLAY\_CLEAR   | 0\|1       | Disable clearing of displays on page changes                                                                               |
| NO\_LED\_CLEAR       | 0\|1       | Disable turnoff of led on page changes                                                                                     |
| NO\_LABEL\_CLEAR     | 0\|1       | Disbale Label reset on page change                                                                                         |
| UI\_TYPE             | 0\|1\|2\|3 | <p>0 = SPAD Generic UI<br>1 =  Joystick UI<br>2 =  MCP/FCU Style UI<br>3 = Custom UI<br>(can be overwritten per INPUT)</p> |
| DEFAULT\_PANEL       | string     | Name of the Default UI Panel if UI is a split panel                                                                        |
| TARGET\_PANEL        | string     | name of the target ui panel of an in-/output                                                                               |
| NOECHO               | 0\|1       | Disable echoing back changes of Device Data (ADD Command)                                                                  |
| DISPLAY\_STATEUPDATE | 0\|1       | Resend all displayvalues if display is turned on (defaut: false)                                                           |

## Complex Device Options





