---
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# SPAD

## Reset SPAD.neXt license

Delete the file `%APPDATA%\SPAD.neXt\SPAD.neXt.lic`

## How to properly open a Support Ticket

1. Start SPAD.neXt
2. (reproduce problem)
3. in SPAD.neXt click in Settings->Support
4. and either Select **an exiting** ticket from the list and click on UPDATE TICKET or click on Create new ticket
5. Add any info needed and hit submit.

Note: if for reproducing the problem no simulation connection is needed please do so from a fresh SPAD.neXt start without Simulator running.\
If simulator is needed do it after a new start not after a over the pond flight\
It's no joy to gravel through megabytes of unnecessary logfiles if you update the ticket after a 5 hour flight. Processing of such tickets is declined.

## Available SPAD.neXt update channels&#x20;

There are 3 update channels available for SPAD.neXt

* **Release**: This is the public release of SPAD.neXt. Your SPAD.neXt installation will automatically update to it, if your [update subscription](https://www.spadnext.com/discover/discover/updatesubscription.html) is valid for it
* **Beta**: The upcoming pre-release, available only for "Complete Edition"-License users , or when assigned for special tests.&#x20;
* **Alpha**: The current development version of SPAD.neXt. This update channel is invite only for early adopters. To apply for participation, open a ticket from within SPAD.neXt. Development focus of current Alpha version can be reviewed in the SPAD.neXt-Discord in the apropiate #release-faq thread

To change your update channel, head to Settings->Application->Expert in SPAD.neXt.&#x20;

All update channels available to you will be selectable.

{% hint style="warning" %}
Note: All update-channels other than Release **require to join the** [**SPAD.neXt community discord**](https://discord.gg/kZqsKgW74G) **and link your SPAD.neXt license** to your discord user properly. All communitcation for non-release updates is done via discord exclusively.
{% endhint %}

## Windows Defender claiming "Trojan:Script/Wacatac.B!ml" Infection

All releases of SPAD.neXt are virus scanned against the 3 most common scan-engines, and all executables are digitally signed. However sometimes Windows Defender will complain when trying to run e.g. a Plugin-Installer and claim it being infected with "Trojan:Script/Wacatac.B!ml". \
This is a known Problem of how Windows Defender handles compressed files sometimes and usually is a false-positive. \
First countercheck that the digital signature of the file is intact:

* Right click the file and select "Properties"
* Select the tab "digital signature" and confirm it states "signature is valid"

If the signature is intact, you need to update you Windows Defender virus database and clear the detectioncache:

1. Open command prompt as administrator and change directory to c:\Program Files\Windows Defender
2. Run “MpCmdRun.exe -removedefinitions -dynamicsignatures”
3. Run "MpCmdRun.exe -SignatureUpdate"

If the signature is **not** intact. Delete the file immediately and report to support@spadnext.com\
If in doubt, you can always submit the file to Microsoft for analysis.
