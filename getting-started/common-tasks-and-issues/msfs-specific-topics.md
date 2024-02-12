# MSFS Specific Topics



## LVAR Bridge Outdated

If SPAD.neXt keeps complaing that the LVAR Bridge is outdated

1. Download the latest MSFS LVAR Bridge Installer at [https://www.spadnext.com/download/download-spad-next.html](https://www.spadnext.com/download/download-spad-next.html)
2.  Proceed as follows

    * Exit MSFS and SPAD.
    * Delete the folder

    MSFS Store/Xbox Version

    ```
    %LOCALAPPDATA%\Packages\Microsoft.FlightSimulator_8wekyb3d8bbwe\LocalState\packages\spad-bridge-module
    ```

    MSFS Steam Version

    ```
    %APPDATA%\Microsoft Flight Simulator\Packages\spad-bridge-module
    ```

    * Install latest Version of the MSFS LVAR bridge.
    * start MSFS and wait until it's in the mainmenu
    * check that above folder has been recreated

## LAG/FPS spikes with SPAD LVAR Bridge installed

During the first 5 minutes after starting a flight (going beyong ready to fly screen), the SPAD.neXt LVAR bridge will scan for new LVAR regulary. Depending on your system you might notice lagspikes, when this scanning occours.\
You can twek the parameters how this scanning is done by editing the file **spdbridge.ini**, which can be found in \
MSFS Store/Xbox Version

```
%LOCALAPPDATA%\Packages\Microsoft.FlightSimulator_8wekyb3d8bbwe\LocalState\packages\spad-bridge-module\work
```

MSFS Steam Version

```
%APPDATA%\Microsoft Flight Simulator\Packages\spad-bridge-module\work
```

Default contents:\
`[spad]` \
`Version = 4` \
`MaxBatch = 100` \
`MaxLVarSearchTime = 5`\
`MaxDigBatch = 100` \
`MaxDigDepth = 4096`



| Name              | Purpose                                                               |                                                                                                          |
| ----------------- | --------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| MaxLVarSearchTime | Time in minutes the bridge will scan for LVAR after flight is started | Increase it to look for LVAR longer                                                                      |
| MaxDigBatch       | Number of LVAR being scanned every frame                              | Decrease the value to reduce load on sim every fram. For lower end machines a value of 30 is recommended |
| MaxDigDepth       | maximal number of LVAR that will be looked for                        |                                                                                                          |
|                   |                                                                       |                                                                                                          |

