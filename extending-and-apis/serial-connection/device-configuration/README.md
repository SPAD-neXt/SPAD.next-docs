# Device Configuration-Phase

After the device initialisation SPAD.neXt will send the command

`0,CONFIG[,Parameters];`

to the device and start the configuration Phase.

The device can now issue commands to configure the device.

The configuration phase will end when the device ackknowledges with

`0,CONFIG;`

{% hint style="warning" %}
The device will not show up in SPAD.neXt UI before configuration phase is completed
{% endhint %}
