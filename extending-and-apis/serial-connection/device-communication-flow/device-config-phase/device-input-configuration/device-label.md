# Device LABEL

`0,LABEL,<index>,<tag>[,options];`

Creates a label on the UI

### Available options

|                       |                                                                                             |   |
| --------------------- | ------------------------------------------------------------------------------------------- | - |
| DYNLABEL=0\|1         | <p>1 enables dynamic labeltext updates by device or events<br>0 adds a static labeltext</p> |   |
| READONLY=1            | labeltext can only be changed by device                                                     |   |
| LABEL=\<text>         | default labeltext                                                                           |   |
| \[Generic UI Options] |                                                                                             |   |

### Sending label updates

`8,<index>,0,<newtext>;`

Updates the labeltext of the label
