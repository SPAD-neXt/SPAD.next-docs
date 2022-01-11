# L:Vars and H:Events

L:VARs and H:Events are additional Variables and Sim Control events that are not part of the "Standard" events in Sim connect.  This requires an Additional Bridge be installed. \
\
In both Prepar3d and MSFS L:VARs are required so we can work with the Extended capabilities of Add On Aircraft.  This is how all of the complex aircraft will interact data wise for their custom systems implementations.  The most notable being Auto Pilot Data.  Add On Planes need to run their own systems to simulate the modes and functions of the simulation.  Then they "under the hood" take control of the plane and fly it.... Thus we need to gain access to View and Control that Data!\
\
The H:Event is the new JS/HTML Gauge Events found in MSFS which also replaced many of the older simconnect events like the GPS controls commands.  MODs like the  Working Title CJ4 and the Fly By Wire A320 have also required the separation of the Standard Autopilot and Data to allow them to implement their controls.  This meant modifying the commands and Data.  We are able via the Bridge to also send these Commands into the sim.  Additional names in use for this will be WASM Bridge or WASM Module.\
\
If you are interested in understanding all of the different data types the SDK docs are valuable source of info.  [https://docs.flightsimulator.com/html/index.htm#t=Additional\_Information%2FReverse\_Polish\_Notation.htm%23Types](https://docs.flightsimulator.com/html/index.htm#t=Additional\_Information%2FReverse\_Polish\_Notation.htm%23Types)\


{% embed url="https://youtu.be/UHeECsbE6Ew" %}
Install the L:Var and H:Event WASM Bridge
{% endembed %}





{% embed url="https://youtu.be/hSO2RkXNOvI" %}
Getting Started with L:Vars using the CRJ
{% endembed %}



