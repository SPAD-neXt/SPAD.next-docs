---
description: Device default profile configuration
---

# Device PROFILE configuration

Defines a device profile that shall be offered/loaded as default for the device, if no device profile exists in the current SPAD.neXt profile (Device not configured dialog)&#x20;

Syntax: 0,PROFILE,\<SourceType>,\<id>

#### SOURCETYPE

|   |                                                                                                                                                                                             |
| - | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0 | \<ID> will contain snippet-id(s) of a complete device snippet to load from SPAD.neXt online database                                                                                        |
| 1 | \<ID> will contain one snippet-id of a device snippet to load from SPAD.neXt online database, but the user will not be asked for confirmation.                                              |
| 2 | \<ID> will contain one snippet-id of a device snippet to load from SPAD.neXt online database. Any existing device profile in currently loaded SPAD.neXt profile will be **overwritten**.    |
| 3 | \<ID> will contain an url that will be downloaded. The url must return a valid SPAD.neXt device profile. If the url is not reachable or invalid, no default profile will be loaded/offered. |

To provide more than one snippet-id for the user to choose from, seperate the id's by `#`\
`e.g. 123#456#12345`

{% hint style="info" %}
This command is only valid during the configuration phase of the device or from within the device configuration xml
{% endhint %}

Examples

`0,PROFILE,0,4567`

`0,PROFILE,3,http:////pastbin.com//a4JhSw`

{% hint style="danger" %}
`Note the escaped '/' in the URL!`
{% endhint %}
