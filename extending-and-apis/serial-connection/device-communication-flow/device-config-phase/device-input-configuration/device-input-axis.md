---
description: Define a device axis
---

# Device input AXIS

`0,INPUT,<index>,<tag>,AXIS,<Inherit>[,<options>];`

### Avaliable Inherits

`SPAD_AXIS`  defines a SPAD.neXt standard axis with calbration and responsecurve support

### Available Options

|               |                                                                 |                       |
| ------------- | --------------------------------------------------------------- | --------------------- |
| AXIS\_MIN     | Axis minimum value                                              | default: 0            |
| AXIS\_MAX     | Axis maximum value                                              | default: 1024         |
| DIRECTIONFUNC | Value expression to convert normalized value to 0-100% UI value | default: value\*100.0 |

`AXIS_MIN` and `AXIS_MAX` are used to calculate the normalized value (0 .. 1.0) of the axis.

{% hint style="info" %}
MIN can be negative if device has a auto-center axis. E.g (-512 .. 512 ) for a rudder
{% endhint %}

\
The 8-Input commands must send absolute raw values ( Min ... Max ) and not a normalized value!

