# Serial: Device Initialisation

When starting SPAD.neXt, after opening the serial port, it will send an INIT Request to all serial devices configured and expects them to respond within 5 seconds, else the device will be marked as offline/unavailable.

Request from SPAD.neXt:\
`0,INIT,<SerialVersion>,<AppVersion>,<AuthToken>`

`Parameters`\
``

| \<SerialVersion> | <p>Version of the serial protocol supported <br>2 means SPAD.neXt  supports version 1 and version 2<br>The current version is 2</p>                                                                                                                                    |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<AppVersion>    | SPAD.neXt version (e.g. 0.9.12.0 )                                                                                                                                                                                                                                     |
| \<AuthToken>     | A unique ID identifying the SPAD.neXt instance used as authentication tag in AuthenticationCipher (See [http://rweather.github.io/arduinolibs/classAuthenticatedCipher.html](http://rweather.github.io/arduinolibs/classAuthenticatedCipher.html#details) for details) |

Reply from device:\
`0,SPAD,<GUID>,<NAME>,<SerialVersion>,<DeviceVersion>[,<opt1>,...,<optN>;`

| `<GUID>`            |  Unique Identifier identifying the device. It should follow the GUID-Registryformat e.g. "{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729}". To create a GUID you can use this site: [https://www.guidgenerator.com/online-guid-generator.aspx](https://www.guidgenerator.com/online-guid-generator.aspx) (enable braces and hyphens) |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<NAME>             | the human readable name of the device. This will be used throughout the SPAD.neXt UI for everything related to that device                                                                                                                                                                                                  |
| \<SerialVersion>    | Serialversion the device is supporting (Current Version is 2)                                                                                                                                                                                                                                                               |
| \<DeviceVersion>    | Version of the device (Major.Minor\[.Build.Patch])                                                                                                                                                                                                                                                                          |
| \<opt1>,...,\<optN> | optional device option Key=Value pairs (see [OPTIONS](../command-1/command-1-option.md))                                                                                                                                                                                                                                    |

## Options&#x20;

available only in INIT Command. All options are optional\
(all additional [options](../command-1/command-1-option.md) can be added as well)

| Key        | Value              |                                                                       |
| ---------- | ------------------ | --------------------------------------------------------------------- |
| AUTHOR     | \<your authtorkey> |                                                                       |
| ALLOWLOCAL | 0\|1\|2            | where SPAD.neXt will look for device configuration files (default: 0) |
| VID        | string             | The VendorID assigned to the device author.                           |
| PID        | string             | A unique **short** product id for the device.                         |

### AUTHOR

To receive your unique authorkey, issue the command "!deviceinfo" on the SPAD.neXt discord.\
This key will identify you as the device author and enable author-only functions like e.g. editing the device UI or device configuration database.

{% hint style="warning" %}
The authorkey is case-sensitive!
{% endhint %}

### ALLOWLOCAL

The ALLOWLOCAL option controls where SPAD.neXt will search for device configuration files/images etc. before checking the database.

Possible Values:\


0 SPAD.neXt will not search for any local files and will always use the globally defined/published ones from the database, if any.&#x20;

1 SPAD.neXt will first search in %APPDATA%/conf/data\_config/local/devices/\<VID>/\<PID> for configuration files before checking the database.

2 **only if the current user is the author of the device** SPAD.neXt will first search in %APPDATA%/conf/data\_config/local/\<AUTHOR>/\<VID>/\<PID> for configuration files before checking the database

{% hint style="info" %}
if no local configuration exists (or is not allowed), the device sent-configuration will be used always.\
if a local configuration exists (and is allowed) it will always overwrite any device sent configuration!
{% endhint %}

### VID

The VID (or Vendor ID) defines the **author** of a device uniquely in a similar manor to USB devices.\
To prevent duplicate id's you have to request your VID in the SPAD.neXt discord

### PID

The PID (or Product ID) defines a **device** uniquely in a similar manor to USB devices.

The PID should be unique per device as it will be also used to find the corresponding device profile within a SPAD.neXt profile.

{% hint style="warning" %}
The PID will be used in SPAD.neXt all over the place (e.g. Variable names), so **keep it short and simpl**e. The only allowed characters for the PID are A-Z,0-9 (no spaces, no special chars)
{% endhint %}

## **Device variables**

if VID **and** PID are defined for a device, all its inputs will be available as LOCAL variables within SPAD.neXt as\
LOCAL:\<VID>\_\<PID>\_\<TAG>\[suffix]\
\[suffix] will only be present if more than one identical device is connected

#### Example

LOCAL:SHAKEPRINT_ECHOBUTTON1_\
_LOCAL:C0NNEX\_FCU\_I\_AP1_

## **INIT Example**

Request: `0,INIT,2,0.9.10.0,73993732632;`\
Reply (go ahead): `0,SPAD,{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729},Altimeter Display,2,1.0;`\
Reply (error): `0,ERROR,<message>;` (e.g. version not supported)

Request: `0,INIT,2,0.9.10.0,73993732632;`\
Reply (go ahead): `0,SPAD,{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729},Altimeter Display,2,1.0,AUTHOR=a3dhfc4323dca`

