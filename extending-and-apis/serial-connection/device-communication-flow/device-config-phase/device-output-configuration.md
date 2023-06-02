---
description: Define a device output descriptor (SPAD -> Device)
---

# Device OUTPUT Configuration

For defining an output descriptor the following command syntax is used:

```
0,OUTPUT,<DeviceIndex>,<Tag>,<Type>,<Inherits>[,<Option>=<Value>,...];
```

\<DeviceIndex> is the numercial index the output should be used by SPAD when sending updates to the device (See [LED](../../device-led-update-channel-6.md) / [DISPLAY ](../../device-display-update-channel-7.md)update   ). For Led commonly the pin on the device can be used as \<DeviceIndex>. This way no more internal processing needs to be done on the device. \
The \<DeviceIndex> should be unique per \<Type>

\<Tag> being the internal name SPAD.neXt should use for events bound to that output descriptor. \<Tag>'s must be unique device wide. It's generally a good idea to give the \<TAG> a prefix (e.g. `L_` for led and `D_` for Displays)

\<Type> the type of the output descriptor\
Currently there are two types of output descriptors  supported:

`LED` an led that has either only a ON/OFF state or a multi color LED

`DISPLAY` any kind of display&#x20;

\<Inherits> is a list of base configurations the output shall use within SPAD.neXt. This decides about the events available for the output and the behaviour.

## Device output LED

A led is a simple output descriptor that always has at least the state ON or OFF&#x20;

#### Available \<Inherits> for led

`SPAD_LED`  a simple ON/OFF led

`SPAD_LED_3COL` a 3 color led predefined as Red,Green,Yellow

`SPAD_LED_C` a led with custom defined colors. The option `COLORSET=<Colorset_Index>` must be added to the command to inform SPAD.neXt about the available colors.

#### Available specific options

|             |                                                                           |                                                                                                                                                                     |
| ----------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DYNLABEL=1  | Enabled updates of the led-labeltext (UI\_FACE=2) via events              |                                                                                                                                                                     |
| UI\_FACE=0  | A round led that changed fillcolor depending on it's state                |                                                                                                                                                                     |
| UI\_FACE=1  | A rectangular led that changes foreground-color depending on it's state   | `FOREGROUND=Red`                                                                                                                                                    |
| UI\_FACE=2  | A rectangular led that can change fore/background depending on it's state | <p><code>FOREGROUND.ON=Red</code><br><code>FOREGROUND.OFF=LightGray</code><br><code>BACKGROUND.ON=Transparent</code><br><code>BACKGROUND.OFF=Transparent</code></p> |
| UI\_FACE=3  | Use custom provided images                                                |                                                                                                                                                                     |
| NOIMG=1     | No background image                                                       |                                                                                                                                                                     |
| COL\_0      | Color of OFF in UI (UI\_FACE != 3)                                        | LightGray                                                                                                                                                           |
| COL\_1      | Color of ON in UI (UI\_FACE != 3)                                         | Yellow or #FFFF00                                                                                                                                                   |
| IMG\_OFF    | Image for OFF (UI\_FACE = 3)                                              | \_PanelImages/LED\_OFF.png                                                                                                                                          |
| IMG\_ON     | Image for ON (UI\_FACE = 3)                                               | \_PanelImages/LED\_ON.png                                                                                                                                           |

### Examples

`0,OUTPUT,1,L_LED1,LED,SPAD_LED;` defines a ON/OFF led with tag `L_LED1` and index 1

`0,OUTPUT,2,L_LED2,LED,SPAD_LED_3COL;` defines a 3-color led with tag `L_LED2` and index 2

`0,OUTPUT,3,L_LED3,LED,SPAD_LED_C,COLORSET=1;` defines a custom led with tag `L_LED3` and index 3 using the defined colorset 1 (See COLORSET)

## Device output DISPLAY

A display is any kind of alphanumerical output. It can e.g. be a 7-Segemnt lcd or a complex display with 5 rows of 20 characters each

The only available \<Inherits> for a display is

`SPAD_DISPLAY`

All configuration is done via the options:

<table><thead><tr><th width="269.3333333333333">Option</th><th width="223.50597609561754">Value</th><th>Description</th></tr></thead><tbody><tr><td>LENGTH</td><td>integer</td><td>Length of each row in characters</td></tr><tr><td>ROWS</td><td>integer</td><td>number of rows</td></tr><tr><td>SEGMENTS</td><td>integer</td><td>number of segements per row. Each segments will be LENGTH/SEGEMENTS width (Default: 0)</td></tr><tr><td>DEFAULT</td><td>any</td><td>Default value to display</td></tr><tr><td>NOPADDING</td><td>0|1</td><td>Disable padding and aligment of output values</td></tr><tr><td>NOSEGMENTROWEVENTS</td><td>0|1</td><td>SPAD will only send updates per row, not per segment</td></tr><tr><td>SEGMENTALIGN</td><td>LEFT|RIGHT (... per segment)</td><td>Alignment of segment value (Default: Right)</td></tr><tr><td>TEXTALIGN</td><td>LEFT|RIGHT</td><td>Aligment of row (Default: right)</td></tr><tr><td><code>FONT</code></td><td>string</td><td>Name of the font to use (Default: Builtin LCD Font)</td></tr><tr><td>FOREGROUND</td><td>#RRGGBB</td><td>Forground color (Default: Blue #FFF0F8)</td></tr><tr><td>BACKGROUND</td><td>#RRGGBB</td><td>Background color (Default: Black #000000)</td></tr><tr><td>FONTSIZE</td><td>number</td><td>Size of the UI font (Default: Height of one display row)</td></tr><tr><td>HEIGHT</td><td>number</td><td>Height of display in pixels (UI)</td></tr><tr><td>WIDTH</td><td>number</td><td>Width of display in pixels (UI)</td></tr></tbody></table>

Examples

`0,OUTPUT,1,D_1,DISPLAY,SPAD_DISPLAY,LENGTH=6,ROWS=1,WIDTH=133,HEIGHT=40`

![One row with 6 characters](../../../../.gitbook/assets/Serial\_Display\_1.png)

`0,OUTPUT,1,D_1,DISPLAY,SPAD_DISPLAY,LENGTH=15,ROWS=3,WIDTH=350,HEIGHT=120`

![3 rows woth 15 chars each](../../../../.gitbook/assets/Serial\_Display\_2.png)

`0,OUTPUT,1,D_1,DISPLAY,SPAD_DISPLAY,LENGTH=24,ROWS=12,WIDTH=400,HEIGHT=300,FONTSIZE=16`

![12 Rows with 24 chars each](../../../../.gitbook/assets/Serial\_Display\_3.png)

### Other outputs

Forany other kind of output (e.g. a servo) no output needs to be defined. Just provide a RW-data for the output using the [ADD](../../command-1/#subcommand-add) command and act on the device accordingly to changes to that data
