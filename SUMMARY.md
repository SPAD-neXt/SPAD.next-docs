# Table of contents

* [SPAD.neXt Manual](README.md)
* [About SPAD.neXt](about.md)

## Unsorted

* [Untitled](unsorted/untitled.md)
* [Untitled](unsorted/untitled-1.md)

## Getting Started

* [System Requirements](getting-started/system-requirements.md)
* [Supported hardware](getting-started/supported-hardware/README.md)
  * [Saitek FIP (Flight Instrument Panel)](getting-started/supported-hardware/saitek-fip/README.md)
    * [Saitek FIP: Driver & Function Check](getting-started/supported-hardware/saitek-fip/saitek-fip-function-check.md)
  * [Common Issues](getting-started/supported-hardware/common-issues.md)
* [Installation](getting-started/untitled/README.md)
  * [Simulation Specifc Steps](getting-started/untitled/simulation-specifc-steps/README.md)
    * [SimConnect Configuration](getting-started/untitled/simulation-specifc-steps/simconnect-configuration.md)
* [First Start](getting-started/first-run-the-configuration-wizard/README.md)
  * [Configuration Wizard](getting-started/first-run-the-configuration-wizard/configuration-wizard.md)

## User Interface

* [Untitled](user-interface/untitled.md)

***

* [Guides and Videos](guides-and-videos/README.md)
  * [New User Series](guides-and-videos/new-user-series.md)
  * [L:Vars and H:Events](guides-and-videos/videos-lvar-hevents.md)
  * [Device Specific](guides-and-videos/videos-device-specific/README.md)
    * [Arduino / SPAD Serial](guides-and-videos/videos-device-specific/arduino-spad-serial.md)
    * [Cockpit Master CDU](guides-and-videos/videos-device-specific/cockpit-master-cdu.md)
    * [Honeycomb](guides-and-videos/videos-device-specific/honeycomb.md)
    * [Joystick (Generic HID)](guides-and-videos/videos-device-specific/joystick-generic-hid.md)
    * [RealSimGear](guides-and-videos/videos-device-specific/realsimgear.md)
    * [Saitek/Logitech](guides-and-videos/videos-device-specific/saitek-logitech.md)
    * [Script Panel](guides-and-videos/videos-device-specific/script-panel.md)
    * [Thrustmaster TCA-Q + Addon](guides-and-videos/videos-device-specific/thrustmaster-tca-q-+-addon.md)
    * [Virtual Avionics](guides-and-videos/videos-device-specific/virtual-avionics.md)
    * [vJoy](guides-and-videos/videos-device-specific/vjoy.md)
    * [VRinsight](guides-and-videos/videos-device-specific/videos-vrinsight.md)
  * [Simulation Specific](guides-and-videos/simulation-specific/README.md)
    * [AS CRJ 550/700 (MSFS)](guides-and-videos/simulation-specific/as-crj-550-700-msfs.md)
    * [WT CJ4 (MSFS)](guides-and-videos/simulation-specific/working-title-cj4-msfs.md)
    * [WT G1000 NXi (MSFS)](guides-and-videos/simulation-specific/wt-g1000-nxi-msfs.md)
    * [PMDG 777 (P3D)](guides-and-videos/simulation-specific/videos-pmdg-777-p3d.md)

## General concepts

* [Untitled](general-concepts/untitled.md)

## Features

* [Expressions](features/expressions/README.md)
  * [Values](features/expressions/values.md)
  * [Referencing Simulation Data](features/expressions/referencing-simulation-data.md)
  * [Operators](features/expressions/operators.md)
  * [Functions](features/expressions/functions.md)
* [Tuner Acceleration](features/tuner-acceleration.md)

## Event programming

* [Untitled](event-programming/untitled.md)

## Extending and API's

* [C# Scripting Interface](extending-and-apis/scripting-interface.md)
* [Serial Interface](extending-and-apis/serial-connection/README.md)
  * [Command: 0](extending-and-apis/serial-connection/command-0.md)
  * [Command: 1](extending-and-apis/serial-connection/command-1.md)
  * [Command: 2](extending-and-apis/serial-connection/command-2.md)
  * [Command: 4](extending-and-apis/serial-connection/command-4.md)
  * [Data Updates](extending-and-apis/serial-connection/command-data-updates.md)
  * [Serial V2](extending-and-apis/serial-connection/serial-v2/README.md)
    * [Command: 0,INIT](extending-and-apis/serial-connection/serial-v2/command-0-init.md)
    * [Command: 0,AUTH](extending-and-apis/serial-connection/serial-v2/command-0-auth.md)
    * [Command: 1,INPUT](extending-and-apis/serial-connection/serial-v2/command-1-input/README.md)
      * [Type = AXIS](extending-and-apis/serial-connection/serial-v2/command-1-input/type-axis.md)
      * [Type = ENCODER](extending-and-apis/serial-connection/serial-v2/command-1-input/type-encoder.md)
      * [Type = PUSHBUTTON](extending-and-apis/serial-connection/serial-v2/command-1-input/type-pushbutton.md)
      * [Type = SWITCH](extending-and-apis/serial-connection/serial-v2/command-1-input/type-switch.md)
    * [Command: 1,OUTPUT](extending-and-apis/serial-connection/serial-v2/command-1-output/README.md)
      * [Type = LED](extending-and-apis/serial-connection/serial-v2/command-1-output/type-led.md)
      * [Type = DISPLAY](extending-and-apis/serial-connection/serial-v2/command-1-output/type-display.md)
    * [Command: 1,IMAGE](extending-and-apis/serial-connection/serial-v2/command-1-image.md)
    * [Command: 1,XML](extending-and-apis/serial-connection/serial-v2/command-1-xml.md)
    * [Command: 1,PROFILE](extending-and-apis/serial-connection/serial-v2/command-1-profile.md)
    * [Command: 1,OPTION](extending-and-apis/serial-connection/serial-v2/command-1-option.md)
    * [Command 1,RAISE](extending-and-apis/serial-connection/serial-v2/command-1-raise.md)
    * [Command 1,SWITCHPAGE](extending-and-apis/serial-connection/serial-v2/command-1-switchpage.md)
    * [Command 1,GOTOPAGE](extending-and-apis/serial-connection/serial-v2/command-1-gotopage.md)
    * [Event 2,DISPLAY](extending-and-apis/serial-connection/serial-v2/event-2-display.md)
    * [Event 2,LED](extending-and-apis/serial-connection/serial-v2/event-2-led.md)
    * [Event 2,PAGE](extending-and-apis/serial-connection/serial-v2/event-2-page.md)
* [X-Plane Datarefs & Commands](extending-and-apis/xplane-datarefs.md)

## FAQ

* [Untitled](faq/untitled.md)

***

* [Glossar](glossar.md)

## Old-Docs

* [Old-Getting-Started-Guide](old-docs/old-getting-started-guide.md)
* [Untitled](old-docs/untitled.md)
