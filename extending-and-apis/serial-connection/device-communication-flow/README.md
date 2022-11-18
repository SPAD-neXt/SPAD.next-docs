# Device Communication Flow

Initialization Phase

| SPAD.neXt sends              | Device sends              | Comment                                                                   |
| ---------------------------- | ------------------------- | ------------------------------------------------------------------------- |
| 0,INIT...                    |                           |                                                                           |
|                              | 0,SPAD,...                |                                                                           |
| 0,CONFIG\[,Parameters]       |                           |                                                                           |
|                              | 0,INPUT/OUTPUT/OPTIONS... | Only if device needs to configure anything                                |
|                              | 0,CONFIG;                 | <p>Device Setup completed<br><strong>Needs to be sent always</strong></p> |
| 0,STATESCAN;                 |                           |                                                                           |
|                              | 0,STATESCAN,1;            | see STATESCAN                                                             |
|                              | 8,....;                   | Any scanstate of stateful inputs                                          |
|                              | 0,STATESCAN,2;            |                                                                           |
| (any queued events and data) |                           |                                                                           |
| 0,START;                     |                           |                                                                           |

