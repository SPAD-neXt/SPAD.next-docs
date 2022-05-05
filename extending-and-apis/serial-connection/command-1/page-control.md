---
description: 'Serial: Configuration (1) Page-Control'
---

# Page-Control

If the device supports paging (see [OPTIONS](../device-configuration-phase/device-options.md)), the current page being active can be controlled from the device

## SWITCHPAGE: Switching to a specific Page

Syntax: `1,SWITCHPAGE,<Guid>[,<create>,<name>];`

|           |                                               |
| --------- | --------------------------------------------- |
| \<Guid>   | GUID of the target page                       |
| \<create> | 0 \| 1 , create page if it doe snot exist yet |
| \<name>   | name of the new page                          |

SPAD.neXT will either respond with PAGE-Events or a ERROR

## GOTOPAGE: Navigate absolute or releative

Syntax: `1,GOTOPAGE,<number>,<isrel>;`

### Navigate (absolute) (\<isrel> = 0)

\<number> contains the absolute pagenumber (1..n)

### Navigate (relative) \<istrel> = 1

\<number> contains the number of pages to navigate left ( < 0 ) or right ( > 0 )

{% hint style="info" %}
a rollover to first/last page will be done automatically
{% endhint %}

\


