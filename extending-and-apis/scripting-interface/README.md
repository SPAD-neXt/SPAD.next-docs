The scripting interface is C#6.0 compatible.  

You can check the DemoScript provided.  

Basically you create Classes in a .cs-File for the needed Purposes.  
To ease development it's recommended to use a C#-IDE to develop the Scripts. (e.g. VS 2015 Community edition (free)). Just create a new C#-Class-Library Project and Reference the Assembly "SPAD.Interfaces.dll" from the SPAD.neXt Binaries or Inlcude the Interface-Project from github. (You will need to create your own signing key)
This way you will get Intellisense and can test-compile your script.

All classes that derive from IScript somehow will be considered by SPAD.neXt.  
Classes that inherit IScriptPrivate will never be called by SPAD.neXt  

The following BaseClass-Interfaces (from [SPAD.neXt.Interfaces.Scripting](https://github.com/c0nnex/SPAD.neXt/blob/master/SPAD.Interfaces/Scripting/IScriptValueProvider.cs) ) are supported:  
  
IScriptValueProvider  
Class will work just like a local variable ,and has to provide a method "public double ProvideValue(IApplication app)" which will be called whenever needed.
  
IScriptAction  
Class provides a custom action which can be bound to a Button/Switch.  
When the Event is raised the method "void Execute(IApplication app, ISPADEventArgs eventArgs)" will be called.

Additional Interfaces that you can implement:  

IScriptCreation	 
Class supports Initialization/Deinitialization. E.g. if you want to initialize/store some stuff
Initialize will be called when the object is instantiated , Deinitialize before the object is Disposed.

IScriptActivation (only suitable for Onjects that also implement IScriptAction)  
Class supports activation/deactivation.  
Activate will be called when an event using this Action is activated in a profile
Deactivate will be called when an event using this Action is deactivated in a profile

To provide an object that is no ValueProvider or Action, derive it from IScript and add the additional necessary Interfaces (e.g. IScriptCreation)  

The [IApplication](https://github.com/c0nnex/SPAD.neXt/blob/master/SPAD.Interfaces/IApplication.cs)-Interface given as Parameter is a gateway to some global functions of SPAD.neXt like creating a logger to write to the logfile.  
Comes in handy for debugging:  


    var myLogger = app.GetLogger("myCoolLoggerName");
    myLogger.Error("This will be shown in Logfile");

For checking/viewing the Logfile I recommend a NLog-Compatible LogViewer like e.g. Log4View.  
The LogFormat-String is "${longdate}|${level}|${threadid}|${logger}|${message}"  

To work with Data from the Sim/SPAD.neXt the global [Eventsystem](https://github.com/c0nnex/SPAD.neXt/blob/master/SPAD.Interfaces/Events/IEventSystem.cs)-Object is the key.  

using "EventSystem.GetDataDefinition" you grab a [IDatadefiniton](https://github.com/c0nnex/SPAD.neXt/blob/master/SPAD.Interfaces/Configuration/IDataDefinition.cs) from SPAD.neXt and can read or manipulate the Values. This also will makes sure that your script will be called when the data changes.  

It's a bit try and error right now, but all interfaces exposed in the SPAD.Interfaces Assembly are usable and working.  
(SPAD.neXt uses them itself for all Panels etc)  
Inline-Documentation for the Interfaces will be added over time, as it is needed

Just playaround a bit.
If you need some help getting started, open an issue, describe what you want to do and I'll try to help you :-D
