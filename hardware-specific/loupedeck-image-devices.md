# Loupedeck Image Devices



* Exit SPAD.neXt
* Install SPAD Loupedeck plugin. You will find it in the GamePlugins-folder of SPAD.neXt installation folder
* Restart Loupedeck app
* In Loupedeck Software unhide the SPAD plugin \
  ![](../.gitbook/assets/grafik.png)
* Create a new Loupedeck Profile and drag the Spad-Actions onto the buttons \
  ![](<../.gitbook/assets/grafik (1).png>)
* Buttons should show the Buttonnames on them now on device
* Start SPAD.neXt , make sure WebApi is enabled. (You can check by opening [http://127.0.0.1:28001/](http://127.0.0.1:28001/) , it should show some api page)
* After about 15secs the Loupedeck should show in Panels , and all buttons on device should go blank. (You might also want to enable the "Wait" option in Settings->Devices->Remote Devices)
*   if everything fails, open a ticket and attach

    ```
    %LOCALAPPDATA%\Loupedeck\Logs\plugin_logs\SPAD.log
    ```
