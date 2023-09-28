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





## IF Statement Examples

Simple IF statements can be added to Expressions.  This can reduce the overall number of "scripts/conditional display events" required to be added..

Example Using "multiple" Change Label Actions on a Stream Deck display.  Example is to have the display show the Heading Value of 1-360 however 0 to show as 360 to match how the Garmin PFDs display the Heading Variable Values of 0 as 360.

The First Event will display the value of the VAR exactly as it is (format to always show 3 digits) while the Second Event will set it to a static text of 360 when the Variable value is equal to 0.

![](<../../.gitbook/assets/image (40).png>)Condition of AP Heading Variable "GREATER" than Zero.

![](<../../.gitbook/assets/image (41).png>)Condition of AP Heading Variable "EQUAL" to Zero.



Instead using an if statement in the first Change Label we can achieve this same result

```
// Expression If Example
If( [MSFS:AUTOPILOT HEADING LOCK DIR] == 0, '360', format( [MSFS:AUTOPILOT HEADING LOCK DIR], '000' ) )
```

This will now insert into the Expression box and supply the same result but only requiring a single Action.  The "condition" is now the AP Heading Var on "ANY CHANGE" of value to trigger the update of the display which will run the Expression to display 360 if the value is 0 else it will display the Variable .. but using Format of 3 digits to make sure the display will always have leading Zeros.

![](<../../.gitbook/assets/image (42).png>)
