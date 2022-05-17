---
description: SPAD tells the device to change the status of a LED
---

# Device LED Update (6)

`6,<LEDINDEX>,<ONOFF>,<TAG>[,<COLORNAME>,<COLORVALUE>];`

\<LEDINDEX> is the index the device defined in configuration phase

\<ONOFF> will be 0 or 1 to turn the led off or on

\<TAG> is the tag the device defined in configuration phase

\<COLORNAME> and \<COLORVALUE> are only present for colored led's (3-State or ColorSets)

