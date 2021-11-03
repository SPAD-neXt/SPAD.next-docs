---
description: Set a device specific option
---

# Command: 1,OPTION

1,OPTION,Key=Value\[,Key2=Value,...];

Available options

| Key           | ValueType | Description                                                                                            |
| ------------- | --------- | ------------------------------------------------------------------------------------------------------ |
| OUT\_COOLDOWN | int       | Time in milliseconds SPAD will wait after each send command/data to give the device time to process it |
| PROFILE\_RO   | 0\|1      | If the device profile cannot be edited by the user                                                     |
| PROFILE\_ENC  | 0\|1      | the profile part of the device will be encrypted                                                       |
| ISGENERIC     | 0\|1      | Device will not provice a UI, SPAD wil generate a generic UI                                           |
| PAGESUPPORT   | 0\|1      | If the device supports profile pages                                                                   |
