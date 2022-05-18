---
description: Defining a custom colorset for LED
---

# Device COLORSET configuration

Syntax: `0,COLORSET,<Key>,<Name>=<Value>[,....,<Name>=<Value>]`

`Key` contains the identifier for this colorset.&#x20;

The `Name=Value` pairs contain

`Name` being the displayname of the color in the SPAD.neXt UI

`Value` being a valid color value. A valid color is either a named color (as defined in [KnownColor](https://docs.microsoft.com/en-us/dotnet/api/system.drawing.knowncolor?view=netframework-4.8) ) or a #RRGGBB hexadecimal value (e.g. AliceBlue , #FF0000 )

{% hint style="info" %}
Each color set must not contain a definition for OFF. It will be generated automatically and is internally fixed.
{% endhint %}

Examples

`0,COLORSET,1,Red=Red,Green=Green,Yellow=Yellow,Blue=#0000FF`

`0,COLORSET,MyCoolSetName,Red=Red,Green=Green,Yellow=Yellow,Blue=#0000FF`
