---
description: New Mackie Mode
---

# X-Touch Mini

Since release 0.9.21.1 SPAD.neXt uses the Mackie-Mode for the X-Touch Mini which gives full control over led's and buttons. \
For a guide how to use this new feature see [the video section.](../../guides-and-videos/videos-device-specific/x-touch-mc-mode.md)

SPAD.neXt will attempt to switch the X-Touch Mini into Mackie-Mode automatically, however this might fail. Specially if you are in W11 24H2 Update, which has a known issue with Midi/audio devices.

Switching did **not** work if:

* the Layer A led is on and the MC mode led above it is off
* Button presses are not recognized by SPAD.neXt

First try to unplug the X-Touch and replug it. Then restart SPAD.neXt and see if the device now switched automatically. If it did you are fine now, but keep in mind that you might unplug and replug the device occasionally becasue of that Windows 11 24H2 bug.

If that did not fix it, the X-Touch Mini need to be switched into Mackie-Mode manually:

* Exit SPAD.neXt
* Download (if not already present) [https://mediadl.musictribe.com/download/software/behringer/X-TOUCH/X-TOUCH-EDITORv1.21.zip](https://mediadl.musictribe.com/download/software/behringer/X-TOUCH/X-TOUCH-EDITORv1.21.zip)
* Unzip container and start the x-touch.exe
*   An ui like this should appear\


    <figure><img src="../../.gitbook/assets/grafik.png" alt=""><figcaption><p>X-Touch Editor</p></figcaption></figure>
* Click on the MC Button
* The Layer led should go off and the MC MODE led above it should go on.
* Close the x-touch editor
* Start SPAD.neXt.&#x20;
* All Buttons should be working now.



\
