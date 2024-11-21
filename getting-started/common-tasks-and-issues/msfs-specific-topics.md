# MSFS Specific Topics



## LVAR Bridge Outdated (MSFS 2020)

If SPAD.neXt keeps complaing that the LVAR Bridge is outdated

1. Download the latest MSFS LVAR Bridge Installer at [https://www.spadnext.com/download/download-spad-next.html](https://www.spadnext.com/download/download-spad-next.html)
2. Proceed as follows
3. Exit MSFS 2020 and SPAD.
4.  Delete the any folders named like "spad-bridge-module" in

    MSFS Store/Xbox Version

    ```
    %LOCALAPPDATA%\Packages\Microsoft.FlightSimulator_8wekyb3d8bbwe\LocalState\Packages
    ```

    MSFS Steam Version

    ```
    %APPDATA%\Microsoft Flight Simulator\Packages
    ```
5.  Delete the any folders named like "spad-bridge-module" in your Communty folder.\
    Default lcoations

    MSFS Store/Xbox Version

    ```
    %LOCALAPPDATA%\Packages\Microsoft.FlightSimulator_8wekyb3d8bbwe\LocalCache\Packages\Community
    ```

    MSFS Steam Version

    ```
    %APPDATA%\Microsoft Flight Simulator\Packages\Community
    ```
6. Install latest Version of the MSFS LVAR bridge and select MSFS 2020 Location
7. start MSFS 2020 and wait until it's in the mainmenu
8. start SPAD.neXt

## LVAR Bridge Outdated (MSFS 2024)

If SPAD.neXt keeps complaing that the LVAR Bridge is outdated

1. Download the latest MSFS LVAR Bridge Installer at [https://www.spadnext.com/download/download-spad-next.html](https://www.spadnext.com/download/download-spad-next.html)
2. Exit MSFS 2024 and SPAD.
3.  Delete the any folders named like "spad-bridge-module" in subdirs of

    MSFS Store/Xbox Version

    ```
    %LOCALAPPDATA%\Packages\Microsoft.Limitless_8wekyb3d8bbwe\LocalState\WASM
    ```

    MSFS Steam Version

    ```
    %APPDATA%\Microsoft Flight Simulator\Packages\WASM
    ```
4.  Delete the any folders named like "spad-bridge-module" in your Communty folder.\
    Default lcoations

    MSFS Store/Xbox Version

    ```
    %LOCALAPPDATA%\Packages\Microsoft.Limitless_8wekyb3d8bbwe\LocalCache\Packages\Community
    ```

    MSFS Steam Version

    ```
    %APPDATA%\Microsoft Flight Simulator\Packages\Community
    ```
5. Install latest Version of the MSFS LVAR bridge and select MSFS 2024 Location
6. start MSFS 2024 and wait until it's in the mainmenu
7. start SPAD.neXt

## LAG/FPS spikes with SPAD LVAR Bridge installed

During the first 5 minutes after starting a flight (going beyong ready to fly screen), the SPAD.neXt LVAR bridge will scan for new LVAR regulary. Depending on your system you might notice lagspikes, when this scanning occours.\
You can tweak the parameters how this scanning is done by editing the Parameters in Settings->Application->MSFS within SPAD.neXt

| Name              | Purpose                                                               |                                                      |
| ----------------- | --------------------------------------------------------------------- | ---------------------------------------------------- |
| MaxLVarSearchTime | Time in minutes the bridge will scan for LVAR after flight is started | Increase it to look for LVAR longer                  |
| MaxDigBatch       | Number of LVAR being scanned every frame                              | Decrease the value to reduce load on sim every fram. |
| MaxDigDepth       | maximal number of LVAR that will be looked for                        |                                                      |
|                   |                                                                       |                                                      |

