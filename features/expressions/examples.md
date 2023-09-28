---
description: Updated when interesting Examples have been Given in Discord
---

# Examples

Converting Time from Sim Vars:\
![](../../.gitbook/assets/image.png)

Example involves using the GPS ETA or ETE and getting conversion to a clean Hours : Minutes : Seconds.  The Expression can use a combination of two functions to convert the Variable.

```
// Format and Timespan

Format(Timespan ([SIMCONNECT:GPS ETE]*1000), 'hh:mm:ss') 
```
