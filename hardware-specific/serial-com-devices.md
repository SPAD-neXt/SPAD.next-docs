# Serial (COM) Devices

SPAD.neXt supports a wide range if serial (COM) devices, however there are many different serial chipsets around, specially for USB2Serial devices.

Some of those chipset require a special treatment (notably the fake CH340 chipset), which you can configure in the serial device setup.

<figure><img src="../.gitbook/assets/grafik (1) (1).png" alt=""><figcaption><p>Serial Device Configuration</p></figcaption></figure>

Select the appropiate Port and Protocol. For some protocols (e.g. VRInsight) no options will be available.

### Speed

If you notice grabage being sent/received then lower the speed. For an USB2Serial device 115200 is usually a good choice, but if the device is too slow to handle this speed, lower it.

### Enable DTR

Data Terminal Ready - It telsl the device that something is connected to it's serial port.\
This should be ON in most of the cases.

{% hint style="warning" %}
Exception: If the device is CH340 based, this has to be set to OFF, because the DTR signal will make the device reset.
{% endhint %}

### Enable RTS/CTS

RequestToSend/ClearToSend Signaling\
A hardware handshake protocol to ensure no data is lost in transmission because of a buffer overrun on the device. In most of the cases this should be set to ON. If you device does not seem to send/receive any data, set it to OFF

{% hint style="warning" %}
For CH340 based devices this has to be turned off, unless it's configured in the device's firmware.
{% endhint %}

### Device wakeup time

Time in ms before spad will try to send anything to the device after opening the port.\
For a real USB2Serial chipset this is not needed (set to 0).\
However e.g. the CH340 fake serial chip has an odd bootloader which will go into device-programming mode if anything is received on the port while device is booting up and in result the device will not respond to any data sent to it.\
If that happens, set this wakeup time. You might need to experiment with the settings but 2000ms is a good starting point. Devices with a lot of stuff in it (e.g. displays) might need a longer wakeup time (e.g. 3500ms).\\

## Common Issues

### Access to ComPort denied

If you get "Access to ComX is denied" error when starting SPAD.neXt after a fresh computer reboot with a serial device, this is most likely because you have Skype or the Arduino IDE running. Serial devices are recognized as audiodevices and locked by skype for unknown reason.\
(Same can appliy to other software locking up the port)

**Solution**: Unplug serial usb and replug it, this will release the lock on it.
