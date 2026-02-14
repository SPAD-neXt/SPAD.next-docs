---
description: vDeck - virtual Streamdeck
---

# vDeck

{% hint style="danger" %}
Note: SPAD.neXt uses the Windows built-in web-access methods to expose the vdeck to your network. To be able to access a virtual device from another computer in your network, you need to open TCP port 28001 in your firewall for your local network. (Not just SPAD.neXt.exe! The port must be open!)
{% endhint %}

(Work in Progress)

Add a vDeck in Settings->Devices->Virtual Devices

* It behaves exactly like a streamdeck
* Click on the detach button to open it as a web device
* For remote access open "http://`ipofSPAD`:28001/VDCK0001.html" in a browser
* Note: `ipofSPAD` is the IP address the computer running spad is on.  This is not 127.0.0.1 that is the localhost ip address only accessible to applicaitons running locally on the machine
  * ### How to Find PC IP - Command Prompt
    1. Press **Windows key + R**
    2. Type **`cmd`** and press **Enter**
    3. In the black window, type `ipconfig` and press **Enter**
    4. Look for:
       * **IPv4 Address** → This is your computer’s local IP address\
         (Example: `192.168.1.15`)

## Customization

(Current vDeck version: 6 )

* you can customize the webinterface by editing Documents/SPAD.neXt/html/VDCK0001.html
* if you customize the html or global css (vdck.css) and want to prevent spad overwriting your changes create a file "VDCK0001.html.disableUpdates"/"vdck.css.disableUpdates". Be aware that this might break functionallity in future updates.
* each vDeck has it's own additional VDECKXXXX.css for customizing. See the corresponding file for a detailed description
* if the html contains an element with id "spad-pagename" its content will be set to the name of the current page
* if the html contains an element with id "spad-profilename" its content will be set to the name of the current profile
* the title of the page will be automatically set to "Profilename / Pagename"

## Double events on older touch devices

Some older touch devices send click and touch events. If you experience events being executed twice you can disable either mouse or touch events in the settings of the vDeck.

