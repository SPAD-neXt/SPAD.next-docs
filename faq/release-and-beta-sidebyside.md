
#Running release and beta side by side
release and beta are config-compatible, no need to duplicate profiles, however it is strongly recommended to run Beta and Release separate from each other because a beta is a beta and bugs can and will happen. 
It will contain bugs, and depending on current source state it might take a week or two until a game-breaking bug is is fixed.

**Preparations**
* Create a subdirectory somewhere where the beta-version will live (e.g. D:\SPAD-Beta)
* Create a "bin" subdirectory (D:\SPAD-Beta\bin) 
* Create a "logs" subdirectory (D:\SPAD-Beta\logs) 
* Create a "conf" subdirectory (D:\SPAD-Beta\conf) 
* Optional: If you want seperate beta profiles:
  * Create a "profiles" subdirectory (D:\SPAD-Beta\profiles)

**Content copy**
* Copy all contents from %APPDATA%/SPAD.neXt/conf to D:\SPAD-Beta\conf
* Copy the complete SPAD.neXt installation directory contents including subfolders (C:\Program Files\SPAD.neXt) to D:\SPAD-Beta\bin
* copy "%APPDATA%/SPAD.neXt/SPAD.neXt.conf" to D:\SPAD-Beta
* Optional: If you want seperate alpha profiles:
  * Copy Documents/SPAD.neXt/profiles to D:\SPAD-Beta\profiles

**Configuration Step 1**
* Open Windows File Explorer, navigate to "%LOCALAPPDATA%/SPAD.neXt"
* Make a copy of the "RELEASE"-Folder and name it "BETA"
* In BETA-Folder edit the file "directories.json" in you favorite text editor. 
* Change "Data" entry to D:/SPAD-Beta
* Change "Logs" entry to D:/SPAD-Beta/logs
* Change "Configuration" entry to D:/SPAD-Beta/conf
* Optional: If you want separate beta profiles:
  * Change "profiles" entry to D:/SPAD-Beta/profiles
* **Important: you must either escape "\\" (backslash) by  "\\\\" , or use "/" to separate path-fragments**

**Configuration Step 2**
* Edit "D:\SPAD-Beta\SPAD.neXt.conf" in your favorite text editor
* Find the ```<Option Key="Application.UpdateChannel" Value="Release" />```  line and change it to ```<Option Key="Application.UpdateChannel" Value="Beta" />```

**Profit**
* Start SPAD.next.exe from D:\SPAD-Beta\bin. It will automatically update 
* Always 3 Green
