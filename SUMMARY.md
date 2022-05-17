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
  * [Common Issues](getting-started/supported-hardware/common-issues/README.md)
    * [USB HUB Requirements](getting-started/supported-hardware/common-issues/usb-hub-requirements.md)
* [Installation](getting-started/untitled/README.md)
  * [Simulation Specifc Steps](getting-started/untitled/simulation-specifc-steps/README.md)
    * [SimConnect Configuration](getting-started/untitled/simulation-specifc-steps/simconnect-configuration.md)
* [First Start](getting-started/first-run-the-configuration-wizard/README.md)
  * [Configuration Wizard](getting-started/first-run-the-configuration-wizard/configuration-wizard.md)

## User Interface

* [UI Familiarization](user-interface/untitled/README.md)
  * [Home Page](user-interface/untitled/home-page.md)
  * [Profiles Page](user-interface/untitled/profiles-page.md)

***

* [Guides and Videos](guides-and-videos/README.md)
  * [New User Series](guides-and-videos/new-user-series.md)
  * [L:Vars and H:Events](guides-and-videos/videos-lvar-hevents.md)
  * [Features & Functions](guides-and-videos/features-and-functions.md)
  * [Device Specific](guides-and-videos/videos-device-specific/README.md)
    * [Arduino / SPAD Serial](guides-and-videos/videos-device-specific/arduino-spad-serial.md)
    * [Cockpit Master CDU](guides-and-videos/videos-device-specific/cockpit-master-cdu.md)
    * [Honeycomb](guides-and-videos/videos-device-specific/honeycomb.md)
    * [Joystick (Generic HID)](guides-and-videos/videos-device-specific/joystick-generic-hid.md)
    * [RealSimGear](guides-and-videos/videos-device-specific/realsimgear.md)
    * [Saitek/Logitech](guides-and-videos/videos-device-specific/saitek-logitech.md)
    * [Script Panel](guides-and-videos/videos-device-specific/script-panel.md)
    * [Stream Deck](guides-and-videos/videos-device-specific/stream-deck.md)
    * [Thrustmaster TCA](guides-and-videos/videos-device-specific/thrustmaster-tca-q-+-addon.md)
    * [vFIP](guides-and-videos/videos-device-specific/vfip.md)
    * [Virtual Avionics](guides-and-videos/videos-device-specific/virtual-avionics.md)
    * [vJoy](guides-and-videos/videos-device-specific/vjoy.md)
    * [VRinsight](guides-and-videos/videos-device-specific/videos-vrinsight.md)
  * [Simulation Specific](guides-and-videos/simulation-specific/README.md)
    * [AS CRJ 550/700/900/1000 (MSFS)](guides-and-videos/simulation-specific/as-crj-550-700-msfs.md)
    * [FBW A32NX (MSFS)](guides-and-videos/simulation-specific/fbw-a32nx-msfs.md)
    * [FSW C414AW](guides-and-videos/simulation-specific/fsw-c414aw.md)
    * [PMDG 737 (MSFS)](guides-and-videos/simulation-specific/pmdg-737-msfs.md)
    * [SWS Kodiak (MSFS)](guides-and-videos/simulation-specific/sws-kodiak-msfs.md)
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

* [Gauges and Extensions](extending-and-apis/gauges-and-extensions.md)
* [C# Scripting Interface](extending-and-apis/scripting-interface.md)
* [Device Interface](extending-and-apis/serial-connection/README.md)
  * [Device Communication Flow](extending-and-apis/serial-connection/device-communication-flow.md)
  * [Device Initialisation](extending-and-apis/serial-connection/device-initialisation.md)
  * [Device Configuration-Phase](extending-and-apis/serial-connection/device-configuration/README.md)
    * [Device options](extending-and-apis/serial-connection/device-configuration/device-options.md)
    * [Device COLORSET configuration](extending-and-apis/serial-connection/device-configuration-phase/device-colorset-configuration.md)
    * [Device PROFILE configuration](extending-and-apis/serial-connection/device-configuration-phase/device-profile-configuration.md)
    * [Device OUTPUT Configuration](extending-and-apis/serial-connection/device-configuration/device-output-configuration.md)
    * [Device INPUT configuration](extending-and-apis/serial-connection/device-configuration/device-input-configuration/README.md)
      * [Type = AXIS](extending-and-apis/serial-connection/device-configuration/device-input-configuration/type-axis.md)
      * [Type = ENCODER](extending-and-apis/serial-connection/device-configuration/device-input-configuration/type-encoder.md)
      * [Type = PUSHBUTTON](extending-and-apis/serial-connection/device-configuration/device-input-configuration/type-pushbutton.md)
      * [Type = ROTARY](extending-and-apis/serial-connection/device-configuration-phase/device-input-configuration/type-rotary.md)
      * [Type = SWITCH](extending-and-apis/serial-connection/device-configuration/device-input-configuration/type-switch.md)
      * [Type = SWITCH3](extending-and-apis/serial-connection/device-configuration-phase/device-input-configuration/type-switch3.md)
  * [Device General Commands](extending-and-apis/serial-connection/command-0.md)
  * [Device commands](extending-and-apis/serial-connection/command-1/README.md)
    * [Page-Control](extending-and-apis/serial-connection/command-1/page-control.md)
  * [Device SPAD.neXt Events (2)](extending-and-apis/serial-connection/command-2.md)
  * [Device Simulation Events](extending-and-apis/serial-connection/command-4.md)
  * [Device LED Update (6)](extending-and-apis/serial-connection/serial-led-update-6.md)
  * [Device Display Update (7)](extending-and-apis/serial-connection/serial-display-update-7.md)
  * [Device Virtual Power](extending-and-apis/serial-connection/virtual-power.md)
  * [Device Custom UI](extending-and-apis/serial-connection/device-custom-ui.md)
  * [Device HTML UI](extending-and-apis/serial-connection/device-html-ui.md)
  * [Serial V2](extending-and-apis/serial-connection/serial-v2/README.md)
    * [Command 1,RAISE](extending-and-apis/serial-connection/serial-v2/command-1-raise.md)
    * [Command: 0,AUTH](extending-and-apis/serial-connection/serial-v2/command-0-auth.md)
* [X-Plane Datarefs & Commands](extending-and-apis/xplane-datarefs.md)
* [FSUIPC: Custom Offsets](extending-and-apis/fsuipc-custom-offsets.md)

## FAQ

* [Untitled](faq/untitled.md)

***

* [Glossar](glossar.md)

## Old-Docs

* [Old-Getting-Started-Guide](old-docs/old-getting-started-guide.md)
* [Untitled](old-docs/untitled.md)
