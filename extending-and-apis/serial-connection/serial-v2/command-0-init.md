---
description: Changes to INIT Command
---

# Command: 0,INIT

## SUBCOMMAND: INIT

When starting SPAD.neXt will send an INIT Request to all serial devices configured and expects them to respond within 5 seconds, else the device will be marked as offline/unavailable.

Request:\
`0,INIT,<Version>,<ID>;`&#x20;

\<Version> = 2

\<ID> = A unique ID identifying the SPAD instance used as authentication tag in AuthenticationCipher (See [http://rweather.github.io/arduinolibs/classAuthenticatedCipher.html](http://rweather.github.io/arduinolibs/classAuthenticatedCipher.html#details) for details)

Reply:\
`0,SPAD,<GUID>,<NAME>[,Parm1=Value1,Param2=Value2 ...];`\
\<GUID> is a Unique Identifier identifying the device. It should follow the GUID-Registryformat e.g. "{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729}". To create a GUID you can use this site: [https://www.guidgenerator.com/online-guid-generator.aspx](https://www.guidgenerator.com/online-guid-generator.aspx) (enable braces and hyphens)\
\<NAME> is the human readable name of the device. This will be used throughout the SPAD.neXt UI for everything related to that device.

The following optional parameters are accepted:

| Parameter | Description                                                                           | Effect                                                                                                                                                            |
| --------- | ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A=\<ID>   | \<ID> being the designated AuthorID of the Author of the device.                      | If \<ID> matches your AuthorID you will able to edit the device configuration xml (UI etc) from within SPAD.neXt unless the device sends it every time connecting |
| E=\<APL>  | \<APL> being the Authentication-Key of the device if your device is working encrypted | **All further communication from or to the device after the 0,SPAD-Reply will be encrypted**                                                                      |
|           |                                                                                       |                                                                                                                                                                   |



**Example**\
Request: 0,INIT,2,785965487;\


Reply (go ahead):&#x20;

0,SPAD,{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729},Altimeter Display,A=e45f32b5677a31,E=e787b65a543f5671c8767f987cabc;\


Reply (error):&#x20;

`0,ERROR[,Message];` (e.g. version not supported)
