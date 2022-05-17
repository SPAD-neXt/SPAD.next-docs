---
description: Add functionality to inputs and outputs
---

# Device routing: Advanced topics

## Input Routing

Basically every device input is a separate control for SPAD.neXt, however you can re-route inputs in the SPAD.neXt UI to add functionality to one input in the UI.

An additional input is created, and the following options are added to it:

|                      |                                                                                                               |                    |
| -------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------ |
| HIDDEN=1             | Input will not be exposed in the UI                                                                           |                    |
| ROUTETO=\<targettag> | Events from this input will not be handled by the input, but routed to the input associated with \<targettag> | ROUTETO=E\_ENCODER |
|                      |                                                                                                               |                    |

### Example: An Encoder with a Pushbutton

First the Encoder is configured

`0,INPUT,2000,E_HDG,ENCODER,SPAD_ENCODER_ACC;`

Then the pushbutton is configured, telling SPAD.neXt to route it to the encoder

`0,INPUT,7,I_HDG_PUSH,PUSHBUTTON,SPAD_PUSHBUTTON,HIDDEN=1,ROUTETO=E_HDG;`

SPAD.neXt will now add the pushbutton-events to the encoder in the UI, and not expose the pushbutton I\_HDG\_PUSH in the UI at all. Whenever the device sends now an inputevent (`8,7,1;`) for that pushbutton, the according events on the encoder will be executed.

### Example: An encoder that can be pulled out as a switch

Again,just configure the encoder and the additional switch

`0,INPUT,2000,E_HDG,ENCODER,SPAD_ENCODER_ACC;`\
`0,INPUT,7,S_HDG_PULL,SWITCH,SPAD_SWITCH,HIDDEN=1,ROUTETO=E_HDG;`\
``

### Complex Examples

#### Example: Encoder that can be pushed and pulled as a pushbutton&#x20;

Now things get a bit more complicated.

First, as before the encoder is configured

`0,INPUT,2000,E_HDG,ENCODER,SPAD_ENCODER_ACC;`

Now 2 additional inputs shall be attached to the encoder that will use the same events. SPAD.neXt needs to know what to do and how to separate the events. To achieve this, additonal options can be added to the input(s) to create diffrent events for each of them:

| Option             | Default   |   |
| ------------------ | --------- | - |
| `ROUTETO.PRESSIMM` | PRESSIMM  |   |
| ROUTETO.PRESS      | PRESS     |   |
| ROUTETO.PRESSLONG  | PRESSLONG |   |
| ROUTETO.HELD       | HELD      |   |
| ROUTETO.RELEASE    | RELEASE   |   |

Literally every event from an input can be rerouted this way. For a switch the options would be `ROUTETO.SWITCHON` , `ROUTETO.SWITCHOFF` , for stateful input (rotary/3-way) those would be `ROUTETO.<positionname>`

{% hint style="success" %}
The option-value will be used as event name in SPAD.neXt. If it does not exist yet, it will be automatically created.
{% endhint %}

But back to the example, now create the 2 additional input buttons  (simple ones to keep this short and simple):

`0,INPUT,7,I_HDG_PUSH,PUSHBUTTON_NOMODE,,HIDDEN=1,ROUTETO=E_HDG,ROUTETO.PRESS=PUSH_PRESS,ROUTETO.RELEASE=PUSH_RELEASE;`

`0,INPUT,8,I_HDG_PULL,PUSHBUTTON_NOMODE,,HIDDEN=1,ROUTETO=E_HDG,ROUTETO.PRESS=PULL_PRESS,ROUTETO.RELEASE=IGNORE;`

{% hint style="warning" %}
Note that the INHERIT for the button are ommited, to prevent SPAD.neXt to add any default events to the buttons.
{% endhint %}

For the pull-button SPAD.neXt is instructed to ignore the release event and only support the push event. The value "IGNORE" can also be ommited which will have the same effect.

In the SPAD.neXt UI the E\_HDG encoder will now have the events `CW / CCW / PUSH_PRESS / PUSH_RELEASE / PULL_PRESS`

{% hint style="danger" %}
Note: This can become quite long configuration commands and should be done in the device editor/ device xml configuration to preserve device space
{% endhint %}

{% hint style="info" %}
Important!\
Routed inputs still have their own variables to hold their current value!
{% endhint %}

#### Example: Airbus FCU Altitude encoder

The Airbus FCU altitude encoder has following addtional functions:\
Push , Pull and a ring-switch for 100 / 1000 steps

`0,INPUT,1000,E_ALT,ENCODER,SPAD_ENCODER_ACC;`

`0,INPUT,1,I_ALT_PUSH,PUSHBUTTON_NOMODE,,HIDDEN=1,ROUTETO=E_ALT,ROUTETO.PRESS=PUSH,ROUTETO.RELEASE=;`

`0,INPUT,2,I_ALT_PULL,PUSHBUTTON_NOMODE,,HIDDEN=1,ROUTETO=E_ALT,ROUTETO.PRESS=PULL,ROUTETO.RELEASE=;`

`0,INPUT,3,S_ALT_RING,SWITCH,,HIDDEN=1,ROUTETO=E_ALT,ROUTETO.SWITCHON=ALT100,ROUTETO.SWITCHOFF=ALT1000;`

The E\_ALT encoder will have the events

`CW / CCW / PUSH / PULL / ALT100 / ALT1000`

{% hint style="warning" %}
Note that the INHERIT for the buttons`/switch` are ommited, to prevent SPAD.neXt to add any default events to the buttons.
{% endhint %}

## Output routing

The other way around is an output that physically located on a button (e.g. MCP / FCU). Here SPAD.neXt needs to know not to expose the led in the UI, but add it to another input, while keeping the output events separated

Again the led will need to have the `HIDDEN=1` option so it will not be exposed in the UI, but now the button needs an option to associate it with the led. This is done by adding the option `LED=<ledtargettag>` to it.

### Example: FCU AP1 button

`0,INPUT,8,I_AP1,PUSHBUTTON,SPAD_PUSHBUTTON,LED=L_AP1;`

`0,OUTPUT,5,L_AP1,LED,SPAD_LED;`

This will add the led-control actions to the button, but when executed they will be routed to the `L_AP1` led using the led-update channel (6)

