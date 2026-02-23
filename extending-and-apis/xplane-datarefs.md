# X-Plane Datarefs & Commands

{% hint style="info" %}
Since version 0.9.24 SPAD.neXt will scan for datarefs and commands automatically for X-Plane 12, if X-Plane and SPAD.neXt are running on the same computer and it is not necessary anymore to create datarefs.txt/commands.txt files.
{% endhint %}

Unfortunately there is no standard way in X-Plane to add data and commands to an aircraft, so every aircraft developer is doing it differently, and there is no way for SPAD.neXt to query those for X-Plane versions < 12

## Scanning for Datarefs

### DataRef Tool

Download [DataRefTool ](https://datareftool.com).\
Install it as a plugin.\
Then start X-Plane, load the aircraft.\
After exiting X-Plane there will be a X-Plane/preferences/output/drt\_last\_run\_datarefs.txt and one for commands which should list all the aircraft ones.\
\
The files have to be moved to the aircraft folder (see below) and be renamed.

## Adding the datarefs and commands locally.&#x20;

Those are only available for the local installation

### Commands

Create a file "commands.txt" in the directory of the ACF-File of the targeted aircraft. List all commands you wan to expose to SPAD.neXt in this file. The Format of the File is the same as the standard X-Plane commands.txt you can find in "X-Plane 11\Resources\plugins"

Format:

```
command[TAB]description (optional)
```



### Datarefs

Datarefs can be announced by placing them into a file "datarefs.txt"  in the directory of the ACF-File of the targeted aircraft. The Format of the File is the same as the standard X-Plane datarefs.txt you can find in "X-Plane 11\Resources\plugins"\
the First 2 lines of that file will be ignored (X-Plane Header)

Format:



```
dataref[TAB]type[TAB]writeable[TAB]unit[TAB]Description(optional)
sim/cockpit2/radios/actuators/com1_power	int	y	boolean	Com radio 1 off or on, 0 or 1.
```

dataref = name of the dataref e.g. sim/cockpit2/radios/actuators/com1\_power\
type = Type of the dataref typically "float" or "int". For dataref arrays add the size of the array e.g. "int\[12]"\
writable = "y" or "n" if the dataref is writable or readonly\
unit = the unit that dataref is in. This is used as a hint for SPAD.neXt to offer conversions to the user

Limits: \
\* arrays are limited to 140 for performance reasons.\
\* if a dataref is not yet known to X-Plane when the plane is loaded, the SPAD.neXt plugin will retry to find it regularly and announce it to SPAD.neXt

Both files will be read by the X-Plane plugin when the aircraft is loaded.

## Contributing Datarefs to SPAD.neXt

You can publish the collected datrefs and commands to SPAD.neXt for global availability via the online services menu.
