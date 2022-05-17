---
description: Providing a Custom UI for a device
---

# Device Custom UI

All custom UI is defined as SVG or PNG images.&#x20;

### SVG

You can use your favorite editor to create SVG images.&#x20;

As a free online editor [https://boxy-svg.com/](https://boxy-svg.com/) is a good choice

Also the repository at [https://www.svgrepo.com/](https://www.svgrepo.com/) is a good first stop if you are looking for free SVG icons and graphics, or ideas

All common features of SVG can be used, but keep in mind that users might use a diffrent theme than you. Make sure the UI looks ok in both light and dark theme of SPAD.neXt.\
If a SVG does not define a fill-color the button text color of the choosen SPAD.neXt theme will be used.

### PNG

PNG images should be transparent&#x20;

### USAGE

For development, make sure you set the ALLOWLOCAL option and store the svg/png-files in Documents/devices/\<AuthorKey>/\<VID>/\<PID>/

* Subdirectories are supported
* For centralized images you can travel up two directories max. (../../gfx/button.svg)
* File-/Directorynames must not start with an underscore
* SPAD.neXt has some builtin images that can be used (TODO REF)

To have a custom UI for an input being displayed, the following options for an input must be set:

* [ ] WIDTH and HEIGHT should be set. (SVG/PNG will be rescaled to this size automatically, default: 32x32)
* [ ] TOP and LEFT can be set to define the position of the UI element relativ to the UI panel (default 0,0 )
* [ ] UI\_TYPE=3
* [ ] BEHAVIOR is set, if it differs from input-default
* [ ] IMG=\<relativePathAndFilename> (See the BEHAVIOR for any special requirements)
* [ ] The type of the file will be determined by the extension. Only .svg and .png are supported

### BEHAVIOR

The BEHAVIOR option defines how an UI element will behave in the UI if it's activated by a device event

Supported values

#### ROTATE

UI element will rotate around its center point, 15 degrees clockwise/counterclockwise per event

#### ROTATEABSOLUTE

UI element will rotate around its center point, to an angle of 15 \* eventvalue  degrees&#x20;

#### ONOFF

Most commonly used for switches. Two images have to provided:

`IMG_ON` (shown when input is considered ON/PRESSED)

`IMG_OFF` (shown when input is considered OFF/RELEASED)

{% hint style="info" %}
When loading/initializing all inputs are treated as OFF
{% endhint %}

#### HIGHLIGHT&#x20;

default behavior. The UI element will not be modified when activated but hightlighted&#x20;

{% hint style="warning" %}
If the  input is a double encoder/rotary the options\
`IMG_INNER`\
`IMG_OUTER`\
have to be provided
{% endhint %}
