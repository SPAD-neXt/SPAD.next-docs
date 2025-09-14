---
description: vDeck - virtual Streamdeck
---

# vDeck

(Work in Progress, check back later)

Add a vDeck in Settings->Devices->Virtual Devices

* It behaves exactly like a streamdeck
* Click on the detach button to open it as a web device
* you can customize the webinterface by editing Documents/SPAD.neXt/html/VDCK0001.html
* if you customize html or css and want to prevent spad overwriting your changes create a file "vdeck001.html.disableUpdates"/"vdck.css.disableUpdates"
* your must not change the title in the html, as it is used to identify the vdeck to connect to
* For remote access open "http://`ipofSPAD`:28001/VDCK0001.html" in a browser

{% hint style="danger" %}
Note: SPAD.neXt uses the Windows built-in web-access methods to expose the vdeck to your network. To be able to access a virtual device from another computer in your network, you need to open the port 28001 in your firewall for your local network. (Not just SPAD.neXt! The port must be open!)
{% endhint %}
