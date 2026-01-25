# CPFlight Devices

Support for CPFLight devices has been implemented "as it is". Any limitations by the firmware of the devices will apply.

Supported Devices (RS232/USB Versions only currently):\
\* MCP\
\* EFIS (chained)\
\* COM-Panel (chained)\
\* ATC-Panel (chained)

## Configuration

### RS232/USB Version

Add the device as serial device in Settings->Devices->Serial and select CPFlight as protocol

### Ethernet Version

Add the device as serial device in Settings->Devices->Serial, select CPFlight (Ethernet) as protocol and configure ip and port according to the CPFlight manual. (not available yet)

## MCP

### Encoders

You can use the normal Counter-/Clockwise events, to use SPAD-Accelleration like with all other devices. Additionally you can use a ENCODER\_SET event which will use the device-builtin acceleration. In this case use a Send-Simulation-Event action and use "EVENT:VALUE" as the data value to send the value coming form the device to the simulation.\
Due to the firmware handling encoders internally, it might  be that the value displayed on device and simulation might differ.

### A/T Led

The LED is controlled by the firmware and not controllable from SPAD.neXt, however you can control the magnetic lock (pro version) or make the led blink using the CPF\_MCP\_ATDICONNECT Variable.

## COM-Panel

Standby Frequency cannot be addressed from outside.\
Older devices do not support 8khz spacing. \
Usage of device is limited to com frequencies only\
Use VALUE\_SET event with EVENT:VALUE parameter to react on Xfer-button

## EFIS

If both CS and FO Efis are present , global buttons (FPV/MTRS/STD/RST) will only be executed on whichever device announces itself first

## ATC Panel

* The Encoders do not send any events. When turning the encoders the  VALUE\_SET event on the display will be raised. Use EVENT:VALUE in the action to get access to the new Transponder Value.
* The ATC Fail LED is not documented and not controllable yet

## Variables

Some Variables are provided to control behaviour of the devices:

<table><thead><tr><th width="283">Name</th><th>Purpose</th></tr></thead><tbody><tr><td>CPF_MCP_BACKLIGHT</td><td>Controll the backlight of all devices</td></tr><tr><td>CPF_MCP_ATDISCONNECT</td><td>Disconnect the A/T magnetic lock (MCP pro) or blink the A/T Led</td></tr><tr><td>CPF_COMx_SPACING</td><td>Switch between 8 (=0) and 25 (=1) kHz spacing. Defaults to 8khz if device supports it.</td></tr></tbody></table>

