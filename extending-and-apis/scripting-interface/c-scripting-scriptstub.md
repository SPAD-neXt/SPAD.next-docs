# C# Scripting: ScriptStub

Starting with 0.9.18 SPAD.neXt.Interfaces contains an abstract ScriptStub which can be used for easier implementation:

```csharp
/// <summary>
/// A basic Script Stub for free use
/// </summary>
public abstract class ScriptStub : IScript, IScriptCreation
{
    /// <summary>
    /// String to prefix all datat with. Data will be available as LOCAL:[PREFIX]_[name]
    /// </summary>
    protected abstract string ScriptDataPrefix { get; }
    protected abstract void InitializeScript();
    protected abstract void DeinitializeScript();

    /// <summary>
    /// Interface to Application for this Script
    /// </summary>
    protected IApplication Application { get; private set; }
    /// <summary>
    /// Our logger for the script.
    /// </summary>
    protected ILogger ScriptLogger { get; private set; }
    protected CancellationTokenSource CancelTokenSource { get; private set; } = new CancellationTokenSource();
    protected CancellationToken CancelToken => CancelTokenSource.Token;
    
    /// <summary>
    /// The loaded SPAD.neXtprofile has changed
    /// </summary>
    protected EventHandler<IProfile, string> ProfileChanged;
    /// <summary>
    /// The active aircraft/vehicle has changed
    /// </summary>
    protected EventHandler<IAircraft, string> AircraftChanged;
    /// <summary>
    /// A flight has been started
    /// </summary>
    protected EventHandler<ISimulationInterface, IAircraft> FlightStarted;
    /// <summary>
    /// The flight ended
    /// </summary>
    protected EventHandler<ISimulationInterface, SimulationGamestate> FlightEnded;
    /// <summary>
    /// The Simulation gamestate has changed (NewState,OldState)
    /// </summary>
    protected EventHandler<ISimulationInterface,SimulationGamestate, SimulationGamestate> GameStateChanged; 

    private Dictionary<string, IDataDefinition> scriptDataValues = new Dictionary<string, IDataDefinition>(StringComparer.InvariantCultureIgnoreCase);
    public void Initialize(IApplication app)
    {
        Application = app;
        ScriptLogger = app.GetLogger("Script." + ScriptDataPrefix);
        scriptDataValues = new Dictionary<string, IDataDefinition>(StringComparer.InvariantCultureIgnoreCase);
        ScriptLogger.Debug("Initialize");
        Application.RegisterSimulationConnected(simulationConnected);
        Application.ActiveProfileChanged += (s, e) => ProfileChanged?.Invoke(Application.ActiveProfile, e.PropertyName);
        Application.AircraftChanged += (s, e) => AircraftChanged?.Invoke(Application.CurrentAircraft, e.PropertyName);
        SafeCall(() => InitializeScript());
    }

    private void simulationConnected(SimulationConfiguration sender, IValueProvider e)
    {
        if (sender != null && sender.SimulationInterface is ISimulationInterface simulationInterface)
        {
            simulationInterface.SimulationGamestateChanged -= SimulationInterface_SimulationGamestateChanged;
            simulationInterface.SimulationGamestateChanged += SimulationInterface_SimulationGamestateChanged;
        }
    }

    private void SimulationInterface_SimulationGamestateChanged(ISimulationInterface sender, SimulationGamestate newState, SimulationGamestate oldState)
    {
        SafeCall(() =>
        {
            if (newState != oldState)
            {
                if (newState == SimulationGamestate.Flying)
                {
                    FlightStarted?.Invoke(sender, Application.CurrentAircraft);
                }
                else
                {
                    FlightEnded?.Invoke(sender, newState);
                }
            }
            GameStateChanged?.Invoke(sender, oldState, newState);
        });
    }

    public void Deinitialize()
    {
        ScriptLogger.Debug("Deinitialize");
        CancelTokenSource.Cancel();
        SafeCall(() => DeinitializeScript());
        scriptDataValues?.Clear();
        scriptDataValues = null;
    }

    protected IDataDefinition GetOrCreateScriptDataValue(string name)
    {
        if (name.Contains(":"))
        {
            throw new InvalidCastException("Symbol ':' is not allowed in datanames");
        }
        var realName = "LOCAL:" + ScriptDataPrefix + "_" + name;
        if (scriptDataValues.TryGetValue(name, out var data))
            return data;
        data = EventSystem.GetDataDefinition(realName);
        scriptDataValues[name] = data;
        return data;
    }
    protected T GetScriptDataValue<T>(string name, T defaultValue = default)
    {
        var data = GetOrCreateScriptDataValue(name);
        return data.GetValueAs<T>(defaultValue);
    }
    protected void SetScriptDataValue(string name, object value)
    {
        var data = GetOrCreateScriptDataValue(name);
        if (data != null) { data.SetRawValue(value); }
    }

    private void SafeCall(Action _call)
    {
        try
        {
            _call();
        }
        catch (Exception ex)
        {
            ScriptLogger.Error(ex.ToString());
        }
    }
}
```
