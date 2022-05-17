# Device preconfigured definition

To take load from the device and save device rom/flash space the complete configuration of a device (see Configuration Phase) can be preconfigured.

The device.xml can either be created by hand (see device-xml-schema) or using the SPAD.neXt built-in device editor.

When using the device editor, the editor will automatically add all defined input/outputs to the ui and they "just" need to be moved around or new inputs/outputs can be added and configured.\
To simplify the process of creating a basic device.xml without needing the device sending it's config at least once, the device-csv-importer can be used.

Once a `device.xml` is present it's save to remove all 0,INPUT/OUTPUT/OPTION-Commands from the device and just reply with a `0,CONFIG;` in the config phase.

