# Device LABEL

`0,LABEL,<index>,<tag>[,options];`

Creates a label on the UI

{% hint style="info" %}
By default labels are page aware and will store their current value if the page is changed and restore it again, when the page is switched back.
{% endhint %}

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
