# X-Plane Configuration

### X-Plane detection

Wenn running the SPAD.neXXt Configuration Wizard, or installing the SPAD.neXt X-Plane plugin, you will automatically be presented all found X-Plane installtions on the computer.

However if you installed instances of X-Plane manually (e.g. by copying), those cannot be detected automatically  and you will have to tell SPAD.neXt where to find them:

* [ ] Open Windows File-Explorer and navigate to `%LOCALAPPDATA%`
* [ ] There should be a file named `x-plane_install_[versionnumber].txt` (e.g. x-plane\_install\_12.txt) for each x-plane version (10/11/12) you have installed/using
* [ ] If that file is missing create it
* [ ] edit the file for your version and add all paths where you have installed that X-Plane version\
  eg.:\
  `W:\X-Plane 12/`
* [ ] Now SPAD.neXt and the Plugin-Installer should recognize all X-Plane installations.

### X-Plane Plugin Configuration

If SPAD.next and X-Plane are running on different computers, you will have to tell the plugin where SPAD.neXt is running.

First start X-Plane once, and exit it again.

Now head to your X-Plane installation folder and navigate to Output\Preferences

Here you will find a file called "**SPADneXtConnector.sdm**". Open it in your favorite text editor (e.g. notepad)

The file will look like something this (do not delete any additional entries!):

`{`\
&#x20; `"ServerHost": "127.0.0.1",`\
&#x20; `"ServerPort": 8181`\
`}`

replace "127.0.0.1" by the ip (IPv4 or IPv6) of your SPAD.neXt-PC.

The port should be ok, however if the port 8181 on your SPAD.neXt-PC is not available SPAD.neXt will automatically select another one. To find out which one, head to Settings->Application->Expert in SPAD.neXt. You will find an option "Remote Services Port" there and the Port that is being used.

Save the file, and make sure the firewall on the SPAD.neXt-PC has port 8181 open.
