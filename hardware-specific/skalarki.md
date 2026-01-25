# Skalarki

{% hint style="danger" %}
All Skalarki devices as complete edition features
{% endhint %}

SPAD.neXt supports all Skalarki Ltd. devices, however you will need to have Skalarki's ProfilerIO running.

Current supported ProfilerIO version: 5.1.911.1000

Generally all inputs and outputs of all devices can be identified by

`SKALARKI_<device>_<type>_<sublocation>_<name>`

\<type> will either be **I**nput (button/switch) **E**ncoder **D**isplay **L**ed\
For the name, the naming provided by Skalarki is used, even if it might be a bit misleading sometimes.

Throughout this guide several online snippets will be referenced. Those will work with the FlyByWire (FBW) A320 and are actively maintained.

### General

All devices will povide variables for some settings:

| Variable           | Purpose                        | Description                                              |
| ------------------ | ------------------------------ | -------------------------------------------------------- |
| ...\_DEVICE\_POWER | Holds the virtual power state  | defaults to 1 (on) if virtual power handling is disabled |
| ...\_BACKLIGHT     | controls the device backlight  | if supported by device                                   |
|                    |                                |                                                          |



### Skalarki Global

<figure><img src="../.gitbook/assets/grafik (2) (1).png" alt=""><figcaption><p>Skalarki Control Panel</p></figcaption></figure>

Since there are a lot of diffrent devices, it is quite some work, to get the basic power configuration for all of them up and running. This is a repeating boring task, and can lead to heavy work if something needs to be changed.

To help with this task SPAD.neXt has an additional virtual device called "Skalarki Global". It provides 3 variables that you can use to control general behavior of the panels at a central place.

As a reference refer to snippet #7635 which contains the programming for the FBW A320

| Variable                                    | Description                                            | Purpose                                                                |
| ------------------------------------------- | ------------------------------------------------------ | ---------------------------------------------------------------------- |
| LOCAL:SKALARKI\_GLOBAL\_AIRCRAFT\_DC\_POWER | Holds if the aircraft currently has any DC Bus powered | Use as condition for functions  that only work if there is DC power    |
| LOCAL:SKALARKI\_GLOBAL\_AIRCRAFT\_AC\_POWER | Hold if the aircraft currently has any AC Bus powered  | Use as condition for functions that only work if there is AC power     |
| LOCAL:SKALARKI\_GLOBAL\_AIRCRAFT\_POWER     | Holds if any of the AC/DC Bus is currently powered     | Use as condition for functions that work if there is any kind of power |

