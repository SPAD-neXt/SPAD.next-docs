# Referencing Simulation Data

To reference any simulation data in an expression, you can add the reference of the data to an expression by enclosing it in \[]

```
Round(  [SIMCONNECT:AUTOPILOT ALTITUDE LOCK VAR]  / 1000 )
```

The result will be the current value of SIMCONNECT:AUTOPILOT ALTITUDE LOCK VAR (e.g. 10000 (feet) ) divided by 1000 and then rounded to a full number = 10



