---
description: SPAD.neXt generally supports ESP compatible gauges
---

# Gauges and Extensions

Gauges loaded into SPAD.neXt have to match this schema: [`Gauge.xsd`](https://github.com/c0nnex/SPAD.neXt/blob/master/Gauges/gauge.xsd)

RPN Expressions have to be ESP RPN conform!

SPAD.neXt is generally Saitek/Logitech compatible, but it has **NOT** implemented Saitek Bugs:

Saitek gauges require a Non-Space-Character before a closing brace "}" e.g. in if{ statements:\
`if{ someexpression`` `<mark style="color:red;">**`%`**</mark>`} els{ someotherexpression`` `<mark style="color:red;">**`%`**</mark>`}`<br>

SPAD.neXt does **not** support this. You will need to alter the gauge accordingly and remove the <mark style="color:red;">**%**</mark>

### Extensions for (RPN) Expressions

To access any other Data than Simconnect (FSX / P3D / MSFS) use the Dataref-Tag as it is used by SPAD.neXt. Those Datarefs have always the format&#x20;

`RPN Expressions: (PROVIDER:DATREFNAME) or (PROVIDER:DATREFNAME,unit)`\
`SPAD Expressions: [PROVIDER:DATREFNAME] or [PROVIDER:DATREFNAME,unit]`

`If the requested unit does not match the datarefs default unit, SPAD.neXt will automatically convert it to the requested unit, if such a conversion is known`

To access LVAR use the prefix **LVAR: (FSX/P3D/MSFS only)**\
`(LVAR:AB_MCP_AP_ON, Number)`&#x20;

To access FSUIPC Offsets use the Prefix **FSUIPC:**\
(FSUIPC:0000:0AB2, Number)

You can copy a dataref from the data browser to you cilpboard, by selecting it and pressing CTRL-C or the OK Button.

Other examples:

PMDG (P3D):\
`(`PMDG737:1000:010E) `= Glareshield.Mode Control Panel.Altitude`

`ETS2`\
`(SCS:scs/truck/fuel)`\
\
`X-Plane:`\
`(XPLANE:sim/cockpit2/annunciators/afterburner)`<br>

#### Local Variables access

**LOCAL**:VARNAME\
Local var , will not be saved, will be initialized to 0 if it does not exist already<br>

**DEVICE**:VARNAME\
Local var, Value will be _DEVICE-specific_, and will be initialized to the saved value again when the gauge is loaded onto that device. (Same varibale has diffrent value son different FIP devices)

P**ROFILE**:VARNAME \
Local var , Value will be saved to the _PROFILE_ , and will be initialized to the saved value again when the profile is loaded<br>

#### Additional Time-Variables

All time variables as shown [here](https://msdn.microsoft.com/en-us/library/cc526981.aspx#EnvironmentData) can also be used with the "LOCAL:"-Prefix to retrieve the local computer time as UTC/Local.\
To get the local computer hour you would use

```
(LOCAL:LOCAL TIME,Hours)
```

#### Dynamic Images

The Image-Tag supports the following extensions for dynamically changing images:

* Attribute "Dynamic"
* Sub-tag "Value"

Example:

```xml
<Element id="RevBar">
        <Position X="164" Y="144" />
        <Image Name="null1.png" Dynamic="rpm_{VALUE}.png" ImageSizes="472,135,472,135">
           <Value Minimum="1" Maximum="32">(A:RPM) ABS 250 / %</Value>
       </Image>
</Element>
```

#### Dynamic Labels

In order to show numbers on the gauge, SPAD.neXt support an additional sub element: \<Label>

See: Dynamic Labels

#### Extended Button Configuration

To assign a function to a FIP button other than a SimConnect Control Event, you can deliver an extended button configuration together with your gauge.\
Just configure the button as desired within SPAD.neXt, and then export the button configuration (copy to clipboard and save to a file) to a file `BUTTONNAME.bml` in the gauge main directory.\
The following buttons are supported:\
`FIP_BUTTON_S1 - FIP_BUTTON_S6 , FIP_RIGHTDIAL, FIP_LEFTDIAL, FIP_BUTTON_PAGEUP, FIP_BUTTON_PAGEDOWN`

### GaugeSettings

SPAD.neXt also defines an additional tag for providing settings in a gauge:

```
<Gauge>
..
..
..
  <GaugeSettings .....>
  </GaugeSettings>
</Gauge>
```

*
* SPAD.neXt GaugeSettings Sample
