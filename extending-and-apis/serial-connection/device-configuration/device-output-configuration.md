---
description: Define a device output descriptor (SPAD -> Device)
---

# Device OUTPUT Configuration

For defining an output descriptor the following command syntax is used:

```
0,OUTPUT,<DEVICEINDEX>,<TAG>,<TYPE>,<INHERITS>[,Option=Value,...];
```

\<DEVICEINDEX> is the numercial index the output should be used by SPAD when sending updates to the device (See [LED](../serial-led-update-6.md) / [DISPLAY ](../serial-display-update-7.md)update   ). For Led commonly the pin on the device can be used as \<DEVICEINDEX>. This way no more internal processing needs to be done on the device. \
The \<DEVICEINDEX> should be unique per \<TYPE>

\<TAG> being the internal name SPAD.neXt should use for events bound to that output descriptor. \<TAG>'s must be unique device wide. It's generally a good idea to give the \<TAG> a prefix (e.g. `L_` __ for led and `D_` for Displays)

\<TYPE> the type of the output descriptor\
Currently there are two types of output descriptors (\<TYPE>) supported:

`LED` an led that has either only a ON/OFF state or a multi color LED

`DISPLAY` any kind of display&#x20;

\<INHERITS> is a list of base configurations the output shall use within SPAD.neXt. This decides about the events available for the output and the behaviour.

### Type: LED

A led is a simple output descriptor that always has at least the state ON or OFF ``&#x20;

Available \<INHERITS> for led

`SPAD_LED`  a simple ON/OFF led

`SPAD_LED_3COL` a 3 color led predefined as Red,Green,Yellow

`SPAD_LED_C` a led with custom defined colors. The option `COLORSET=<COLORSET_INDEX>` must be added to the command to inform SPAD.neXt about the available colors.

Examples\
`0,OUTPUT,1,L_LED1,LED,SPAD_LED;` defines a ON/OFF led with tag `L_LED1` and index 1

`0,OUTPUT,2,L_LED2,LED,SPAD_LED_3COL;` defines a 3-color led with tag `L_LED2` and index 2

`0,OUTPUT,3,L_LED3,LED,SPAD_LED_C,COLORSET=1;` defines a custom led with tag `L_LED3` and index 3 using the defined colorset 1 (See COLORSET)

### Type: DISPLAY

A display is any kind of alphanumerical output. It can e.g. be a 7-Segemnt lcd or a complex display with 5 rows of 20 characters each

The only available \<INHERITS> for a display is

`SPAD_DISPLAY`

All configuration is done via the options:

| Option             | Value                         | Description                                                                            |
| ------------------ | ----------------------------- | -------------------------------------------------------------------------------------- |
| LENGTH             | integer                       | Length of each row in characters                                                       |
| ROWS               | integer                       | number of rows                                                                         |
| SEGMENTS           | integer                       | number of segements per row. Each segments will be LENGTH/SEGEMENTS width (Default: 0) |
| DEFAULT            | any                           | Default value to display                                                               |
| NOPADDING          | 0\|1                          | Disable padding and aligment of output values                                          |
| NOSEGMENTROWEVENTS | 0\|1                          | SPAD will only send updates per row, not per segment                                   |
| SEGMENTALIGN       | LEFT\|RIGHT (... per segment) | Alignment of segment value (Default: Right)                                            |
| TEXTALIGN          | LEFT\|RIGHT                   | Aligment of row (Default: right)                                                       |
| `FONT`             | string                        | Name of the font to use (Default: Builtin LCD Font)                                    |
| FOREGROUND         | #RRGGBB                       | Forground color (Default: Blue #FFF0F8)                                                |
| BACKGROUND         | #RRGGBB                       | Background color (Default: Black #000000)                                              |
| FONTSIZE           | number                        | Size of the UI font (Default: Height of one display row)                               |
| HEIGHT             | number                        | Height of display in pixels (UI)                                                       |
| WIDTH              | number                        | Width of display in pixels (UI)                                                        |

Examples

`0,OUTPUT,1,DISPLAY,SPAD_DISPLAY,LENGTH=6,ROWS=1,WIDTH=133,HEIGHT=40`

![One row with 6 characters](../../../.gitbook/assets/Serial\_Display\_1.png)

`0,OUTPUT,1,DISPLAY,SPAD_DISPLAY,LENGTH=15,ROWS=3,WIDTH=350,HEIGHT=120`

![3 rows woth 15 chars each](../../../.gitbook/assets/Serial\_Display\_2.png)

`0,OUTPUT,1,DISPLAY,SPAD_DISPLAY,LENGTH=24,ROWS=12,WIDTH=400,HEIGHT=300,FONTSIZE=16`

![12 Rows with 24 chars each](../../../.gitbook/assets/Serial\_Display\_3.png)
