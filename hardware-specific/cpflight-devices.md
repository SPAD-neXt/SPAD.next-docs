# CPFlight Devices

Support for CPFLight devices has been implemented "as it is". Any limitations by the firmware of the devices will apply.

Supported Devices (RS232/USB Versions only currently):\
\* MCP\
\* EFIS (chained)\
\* COM-Panel (chained)

## MCP

### Encoders

You can use the normal Counter-/Clockwise events, to use SPAD-Accelleration like with all other devices. Additionally you can use a ENCODER\_SET event which will use the device-builtin acceleration. In this case use a Send-Simulation-Event action and use "EVENT:VALUE" as the data value to send the value coming form the device to the simulation.\
Due to the firmware handling encoders internally, it might  be that the value displayed on device and simulation might differ.

### A/T Led

The LED is controlled by the firmware and not controllable from SPAD.neXt

## COM-Panel

Standby Frequency cannot be addressed from outside, as well the device does not support 8khz spacing. Usage of device is limited to com frequencies only\
Use VALUE\_SET event with EVENT:VALUE parameter to react on Xfer-button

## EFIS

If both CS and FO Efis are present , global buttons (FPV/MTRS/STD/RST) will only be executed on whichever device announces itself first

## Variables



<table><thead><tr><th width="283">Name</th><th>Purpose</th></tr></thead><tbody><tr><td>CPF_MCP_BACKLIGHT</td><td>Controll the backlight of all devices</td></tr><tr><td>CPF_MCP_ATDISCONNECT</td><td>Disconnect the A/T magnetic lock (MCP pro) or blink the A/T Led</td></tr><tr><td></td><td></td></tr></tbody></table>

## Common Issues

### Access to ComPort denied

If you get "Access to ComX is denied" error when starting SPAD.neXt after a fresh computer reboot with a cpflight device, this is most likely because you have Skype runnung. CPFlight devices are recognized as audiodevices and locked by skype for unknown reason. \
**Solution**: Unplug MCP usb and replug it, then skype will release the lock on it.
