# Midi Devices

#### **Windows 11 24h2 Issues**

Windows Midi driver will go into sleep mode and there is currently no way to prevent that, because you cannot configure usb power options for it. This results in the midi device not sending any input.\
The only known solution is to unplug the device and replug it.

#### Windows 11 25H2 Issues

**Important: This is only for W11 25H2!**&#x20;

Sometime the 25H2 update will not convert midi devices correctly. MS as released a tool to fix this. [https://microsoft.github.io/MIDI/tools/midifixreg/](https://microsoft.github.io/MIDI/tools/midifixreg/)&#x20;

Also make sure the midisrv service is running
