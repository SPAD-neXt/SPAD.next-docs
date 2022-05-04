---
description: Set device specific options
---

# Device options

Syntax: `0,OPTION,Key=Value[,Key2=Value2,...];`

## Simple Device options

Syntax: `Optionkey=Value`

| Key                | ValueType  | Description                                                                                                                |
| ------------------ | ---------- | -------------------------------------------------------------------------------------------------------------------------- |
| OUT\_COOLDOWN      | number     | Time in milliseconds SPAD will wait after each sent command/data to give the device time to process it (Default: 25ms)     |
| PROFILE\_RO        | 0\|1       | If the device profile cannot be edited by the user                                                                         |
| PROFILE\_ENC       | 0\|1       | the profile part of the device will be encrypted                                                                           |
| ISGENERIC          | 0\|1       | Device will not provide any UI, SPAD wil generate a generic UI                                                             |
| PAGESUPPORT        | 0\|1       | If the device supports profile pages                                                                                       |
| NO\_DISPLAY\_CLEAR | 0\|1       | Disable clearing of displays on page changes                                                                               |
| NO\_LED\_CLEAR     | 0\|1       | Disable turnoff of led on page changes                                                                                     |
| UI\_TYPE           | 0\|1\|2\|3 | <p>0 = SPAD Generic UI<br>1 =  Joystick UI<br>2 =  MCP/FCU Style UI<br>3 = Custom UI<br>(can be overwritten per INPUT)</p> |
| DEFAULT\_PANEL     | string     | Name of the Default UI Panel if UI is a split panel                                                                        |
| TARGET\_PANEL      | string     | name of the target ui panel of an in-/output                                                                               |

## Complex Device Options

### PROFILE

To define a device profile that shall be offered/loaded as default for the device, if no device profile exists in the current SPAD.neXt profile (Device not configured dialog) you can procide the PROFILE Option

Syntax: `PROFILE=<SOURCETYPE>=<ID>`

#### SOURCETYPE

| Value |                                                                                                                                                                                            |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 0     | \<ID> will contain snippet-id(s) of a complete device snippet to load from SPAD.neXt online database                                                                                       |
| 1     | \<ID> will contain one snippet-id of a device snippet to load from SPAD.neXt online database, but the user will not be asked for confirmation.                                             |
| 2     | \<ID> will contain one snippet-id of a device snippet to load from SPAD.neXt online database. Any existing device profile in currently loaded SPAD.neXt profile will be overwritten.       |
| 3     | \<ID> will contain an url that will be downloaded. The url must return a valid SPAD.neXt device profile. If the url is not reachable or invalid no default profile will be loaded/offered. |

To provide more than one snippet-id for the user to choose from, seperate the id's by `#`\
`e.g. 123#456#12345`

{% hint style="info" %}
This option is only valid during the configuration phase of the device or from within the device configuration xml
{% endhint %}

Examples

`0,OPTION,PROFILE=0=4567`

`0,OPTION,PROFILE=3=http://pastbin.com/a4JhSw`

