# Device INIT-Phase

When starting SPAD.neXt will send an INIT Request to the device and expects a response within 5 seconds, else the device will be marked as offline/unavailable.

Request from SPAD.neXt:\
`0,INIT,<SerialVersion>,<AppVersion>,<AuthToken>`

`Parameters`\
``

| \<SerialVersion> | <p>Version of the serial protocol supported <br>2 means SPAD.neXt  supports version 1 and version 2<br>The current version is 2</p>                                                                                                                                    |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<AppVersion>    | SPAD.neXt version (e.g. 0.9.12.0 )                                                                                                                                                                                                                                     |
| \<AuthToken>     | A unique ID identifying the SPAD.neXt instance used as authentication tag in AuthenticationCipher (See [http://rweather.github.io/arduinolibs/classAuthenticatedCipher.html](http://rweather.github.io/arduinolibs/classAuthenticatedCipher.html#details) for details) |

Reply from device:\
`0,SPAD,<Guid>,<Name>,<SerialVersion>,<DeviceVersion>[,<opt1>,...,<optN>;`

| `<Guid>`            |  Unique Identifier identifying the device. It should follow the GUID-Registryformat e.g. "{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729}". To create a GUID you can use this site: [https://www.guidgenerator.com/online-guid-generator.aspx](https://www.guidgenerator.com/online-guid-generator.aspx) (enable braces and hyphens) |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<Name>             | the human readable name of the device. This will be used throughout the SPAD.neXt UI for everything related to that device                                                                                                                                                                                                  |
| \<SerialVersion>    | Serialversion the device is supporting (Current Version is 2)                                                                                                                                                                                                                                                               |
| \<DeviceVersion>    | Version of the device (Major.Minor\[.Build.Patch])                                                                                                                                                                                                                                                                          |
| \<opt1>,...,\<optN> | optional device option Key=Value pairs (see [OPTIONS](device-config-phase/device-options.md))                                                                                                                                                                                                                               |

## INIT-Options&#x20;

available only in INIT Command. \
(all additional [options](device-config-phase/device-options.md) can be added as well)

| Key        | Value              |                                                                       |
| ---------- | ------------------ | --------------------------------------------------------------------- |
| AUTHOR     | \<your authtorkey> |                                                                       |
| ALLOWLOCAL | 0\|1\|2            | where SPAD.neXt will look for device configuration files (default: 0) |
| PID        | string             | A unique **short** product id for the device.                         |
| SERIAL     | string             | optional serial number of device                                      |

{% hint style="warning" %}
If PID option is provided, the AUTHOR option must be provided as well
{% endhint %}

### AUTHOR

To receive your unique authorkey, issue the command "!deviceinfo" on the SPAD.neXt discord.\
This key will identify the device author and enable author-only functions like e.g. editing the device UI or device configuration database, if the current SPAD.neXt user is the device author.

{% hint style="warning" %}
The authorkey is case-sensitive!
{% endhint %}

### ALLOWLOCAL

The ALLOWLOCAL option controls where SPAD.neXt will search for device configuration files/images etc. before checking the database.\
_Documents_ refers to the Documents-Directory from SPAD.neXt configuration. Default: "Documents/SPAD.neXt"-Folder of Windows user

SPAD.neXt will search for files/images in the following order \


Value = 0 (default)

&#x20;SPAD.neXt will not search for any local files and will always use&#x20;

1. Internal database
2. Device provided data

Value = 1

1. _Documents_/devices/local/\<VID>/\<PID>/
2. Internal database
3. Device provided data

Value = 2

**if the current SPAD.neXt user is the author of the device, else it will behave like 0**

1. _Documents_/devices/\<AUTHOR>/\<VID>/\<PID>/
2. _Documents_/devices/local/\<VID>/\<PID>/
3. Internal database
4. Device provided data



{% hint style="info" %}
if no local configuration exists (or is not allowed), the device sent-configuration will be used always.\
if a local configuration exists (and is allowed) it will always overwrite any device sent configuration!
{% endhint %}

### VID

The VID (or Vendor ID) defines the **author** of a device uniquely in a similar manor to USB devices.

The VID cannot be chosen freely, but has to be requested by opening a ticket, to prevent duplicates. The VID is provided and set automatically by SPAD.neXt once it has been assigned.

### PID

The PID (or Product ID) defines a **device** uniquely in a similar manor to USB devices.

The PID can be choosen freely and should be unique per device(type) as it will be also used to find the corresponding device profile within a SPAD.neXt profile.

{% hint style="warning" %}
The PID will be used in SPAD.neXt all over the place (e.g. Variable names), so **keep it short and simpl**e. The only allowed characters for the PID are A-Z,0-9 (no spaces, no special chars)
{% endhint %}

### SERIAL

If provided the serial number of the device (unique per device connected!) to identify device variables (ADD Command). If not provided or a duplicate is found, SPAD.neXt will use an internal unique identifier

## **Device variables**

if PID is defined for a device, all its inputs will be available as LOCAL variables within SPAD.neXt as\
`LOCAL:<VID>_<PID>_<TAG>[suffix]`\
\[suffix] will only be present if more than one identical device is connected

#### Examples

`LOCAL:SHAKEPRINT_ECHO_BUTTON1`\
`LOCAL:C0NNEX_FCU_I_AP1`\
`LOCAL:C0NNEX_FCU_I_AP1_2` (second FCU device)

``

## **INIT Examples**

Request from SPAD.neXt: \
`0,INIT,2,0.9.10.0,73993732632;`\
Reply from device: \
`0,SPAD,{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729},Altimeter Display,2,1.0;`\
(No one will be able to locally modify the device configuration)

Request from SPAD.neXt: \
`0,INIT,2,0.9.10.0,73993732632;`\
Reply from device:\
`0,SPAD,{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729},Demo,2,1.0,AUTHOR=a3dhfc4323dca,PID=Echo`\
``The user associated with authorkey a3dhfc4323dca will be able to edit the device configuration. SPAD.neXT will frist search in `Documents/SPAD.neXt/devices/a3dhfc4323dca/shakeprint/echo` for local configurations

