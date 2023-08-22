---
description: 'Appies to: FSX (Box and Steam edition) /  P3D / MSFS'
---

# SimConnect Configuration

SimConnect is a synonym for a protocol Microsoft published together with the FSX Acceleration Pack/SP2. All simulations that are based on FSX (this includes Prepare3D and MS Flight Simulator 2020) support this protocol. For a complete description of SimConnect and its feature please see [Microsoft's ESP Documentation](https://docs.microsoft.com/en-us/previous-versions/microsoft-esp/cc526948\(v=msdn.10\)).

No additional Installation is necessary on any client computer, since SPAD.neXt uses a built-in version of SimConnect. However, if you plan to user additional plugin/software that require SimConnect-Suport you might need to install the SimConnect Client Packages. See the simulator documetation on details.

If you plan to run SPAD.neXt on the same computer as the simulation runs on (common case), then the simulation should have all necessary configuration created already, and you can skip this steps. \
If later in the process of the configuration wizard you run into problems, get back to this pages to check the configrutaion.



## Simconnect configuration file location

In the next paragraphs SIMCONNECT.XML will be referenced. This always references the SimConnect configuration file for the sim and can be found at the following location:

### For FSX (Box Edition)

%APPDATA%\Microsoft\FSX

### For FSX (Steam Edition)

either %APPDATA%\Microsoft\FSX or %APPDATA%\Microsoft\FSX-SE

### For Preapr3D

%APPDATA%\Lockheed Martin\Prepar3D v2

%APPDATA%\Lockheed Martin\Prepar3D v3

%APPDATA%\Lockheed Martin\Prepar3D v4

%APPDATA%\Lockheed Martin\Prepar3D v5

depending on the installed version of Prepar3D

### For MSFS (Store or XBox Gamepass Edition)

%LOCALAPPDATA%\Packages\Microsoft.FlightSimulator\_8wekyb3d8bbwe\LocalCache

### For MSFS (Steam Edition)

%APPDATA%\Microsoft Flight Simulator\Packages

### For MSFS (Box Edition)

%LOCALAPPDATA%\MSFSPackages



## Local Configuration (Sim and SPAD.neXt on same computer)

Run The Configuration Wizard and select the Local pc option.  This is for running SPAD.neXt on the same PC that the simulator is running on.

![](<../../../.gitbook/assets/image (39).png>)

STEP 1:  Detection of local simulators.  if it looks correct then move to the next step.  Pictured here it has found both FSX Steam and MSFS:

![](<../../../.gitbook/assets/image (22).png>)

STEP 2:  SimConnect Detection / Enablement.  Since running locally with the sim then the selection with sim on this computer is desired.

![](<../../../.gitbook/assets/image (28).png>)

Test Connection - you need a simulator running.  In this example MSFS is running when the test is run

![](<../../../.gitbook/assets/image (29).png>)

STEP 3:  FSUIPC Detection.  FSUIPC is not running on this PC thus disable is set.  Note this can be re-enabled from the Settings menu later on if the need for FSUIPC is required.

![](<../../../.gitbook/assets/image (31).png>)

STEP 4:  This is skipped for this installation.

STEP 5:  X-Plane Support.  Enable if you have X-Plane installed but SPAD.neXt did not auto discover it.. else leave disabled.

![](<../../../.gitbook/assets/image (33).png>)

STEP 7: Review selections (note anything can be enabled later in the settings menu manually)

![](<../../../.gitbook/assets/image (24).png>)

Apply Settings and Continue

![](<../../../.gitbook/assets/image (37).png>)

Click Next

![](<../../../.gitbook/assets/image (30).png>)

Click Complete Wizard

![](<../../../.gitbook/assets/image (34).png>)

Changes Require a Restart of SPAD.neXt.   HOWEVER!!! we can install the H:Event and L:Var Bridge before we do that!!  Just make sure that you exit MSFS first (or restart it after running the install.  Like all Community Add Ons MSFS has to see them on initial startup otherwise they won't be loaded until a MSFS Restart!)

Click on Install LVAR Bridge (do this for all Sims you have installed.. example is MSFS..)

![](<../../../.gitbook/assets/image (21).png>)

Click on the NEXT button

![](<../../../.gitbook/assets/image (17).png>)

Click on Install

![](<../../../.gitbook/assets/image (35).png>)

Click on Finish

Now Restart MSFS if it was still Running and Close and Relaunch SPAD.neXt

With MSFS back up and Running and SPAD.neXt Relaunched go to the Status Page to confirm the SimConnect and LVAR Connections:

![](<../../../.gitbook/assets/image (38).png>)

## Remote Configuration (Sim and SPAD.neXt on diffrent computer)

Add The following to your XML File On the PC Running the Sim.  No need to edit a file on the Remote PC.  In this example the IP Address is the Address of the Sim PC.



```
<SimConnect.Comm> 
    <Disabled>False</Disabled> 
    <Protocol>IPv4</Protocol> 
    <Scope>global</Scope> 
    <MaxClients>64</MaxClients> 
    <Address>10.0.1.201</Address> 
    <Port>500</Port>
    <Disablenagle>False</Disablenagle>
</SimConnect.Comm>
```

An easy way to figure out your ip address is to press the WINDOWS key and type in CMD then press  Enter.  This will launch the Command Prompt.

Type in "ipconfig" and press enter

![](<../../../.gitbook/assets/image (1).png>)

RUN The Config Wizard on the Networked PC.  Make sure to select Remote/Network then Start the Wizard.

![](<../../../.gitbook/assets/image (1) (2).png>)

STEP 2:  Add the IP Address and Port number as entered in the Sim PC XML.

![](<../../../.gitbook/assets/image (19).png>)

Run the Test Connection

![](<../../../.gitbook/assets/image (36).png>)

STEP 3: FSUIPC..  this is if you want to be able to link FSUIPC offsets through SPAD.  For Network connection you will need WideFS running.

![](<../../../.gitbook/assets/image (20).png>)

STEP 5: XPlane Support (Note Step 4 is skipped on Network Installs) enable XPlane if you have it on the Sim PC as well .. Note that you can only make 1 connection so unlike MSFS where you could have Local SPAD and Remote SPAD at the same time XPlane can only be 1.. so chose wisely...

![](<../../../.gitbook/assets/image (18).png>)

Click Apply!!  Step 6 is also not required on Network Installations.

![](<../../../.gitbook/assets/image (32).png>)

![](<../../../.gitbook/assets/image (27).png>)

![](<../../../.gitbook/assets/image (23).png>)

Now you will need to restart!

![](<../../../.gitbook/assets/image (25).png>)

Close SPAD.neXt and then Restart it for all the settings to take effect.

IMPORTANT!! \
With a Network Connection where no SPAD.neXt was installed on the Local Sim PC the LVAR Bridge will need to be installed Manually:

Find the LVAR Bridge Installers on the Network PC.\
Default install location -- C:\Program Files\SPAD.neXt\GamePlugins

![](<../../../.gitbook/assets/image (26).png>)

Copy the Bridge Installers to the Sim PC and run them on it.

These are needed for Complex Add On that use L:Vars (Local Variables defined by the simobjects when loaded.. ie when you load up a plane..) And also with MSFS where the new Instruments are JS/HTML and requre the "H:Events" which must pass through the WASM Module and not directly Via SimConnect.

