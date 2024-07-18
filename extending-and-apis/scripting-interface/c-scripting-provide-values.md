---
description: Scripting reference implementation for providing Values to SPAD.neXt
---

# C# Scripting: Provide Values

```csharp
    /// <summary>
    /// A Demo for a script that provides some value(s) to SPAD.neXt
    /// reference Implementation. 
    /// </summary>
    public class ProvideValueDemoScript : ScriptStub
    {
        protected override string ScriptDataPrefix => "DEMO";

        protected override void InitializeScript()
        {
            ScriptLogger.Info("In Init");
            FlightStarted += OnFlightStarted;
            FlightEnded += OnFlightEnded;
            RegisterData();
            workerTask = Task.Run(workerThreadAction, CancelToken);
        }

      

        protected override void DeinitializeScript()
        {
            // Signal to end worker Task is set by base class via the CancelToken already
            // Wait for worker task to gracefully end
            Task.WaitAll(workerTask);
        }

        private bool isFlightStarted = false;
        private Task workerTask = null;
        

        private void RegisterData()
        {
            // Register all the Data's this script provides
            GetOrCreateScriptDataValue("CYCLE"); // => LOCAL:DEMO_CYCLE
        }

        /// <summary>
        /// Increment LOCAL:DEMO_CYCLE by 1 every 1 second
        /// </summary>
        private async Task workerThreadAction()
        {
            while (!CancelToken.IsCancellationRequested)
            {
                if (isFlightStarted)
                {
                    SetScriptDataValue("CYCLE", GetScriptDataValue<int>("CYCLE") + 1);
                }
                await Task.Delay(1000);
            }
        }

        private void OnFlightStarted(ISimulationInterface sender, IAircraft aircraft)
        {
            ScriptLogger.Info($"FlightStarted: {aircraft?.Name} ({sender.SimulationGamestate})");
            isFlightStarted = true;
        }

        private void OnFlightEnded(ISimulationInterface sender, SimulationGamestate newState)
        {
            if (isFlightStarted && newState != SimulationGamestate.Flying)
            {
                ScriptLogger.Info($"Flight end. ({newState})");
                isFlightStarted = false;
                
                SetScriptDataValue("CYCLE", 0);
            }
        }
    }
```

