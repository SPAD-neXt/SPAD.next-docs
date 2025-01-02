# Midi Devices

There is a known issue with **Windows 11 24h2 Update**.&#x20;

Windows Midi driver will go into sleep mode and there is currently no way to prevent that, because you cannot configure usb power options for it. This results in the midi device not sending any input.\
The only known solution is to unplug the device and replug it.
