---
description: Define a stateless encoder
---

# Device input ENCODER

`0,INPUT,<index>,<tag>,ENCODER,<Inherit>[,<options>];`

### Available Inherits&#x20;

|                             |                                                                                |                 |
| --------------------------- | ------------------------------------------------------------------------------ | --------------- |
| `SPAD_ENCODER_NOACC`        | a single encoder with Clockwise/Counterclockwise events                        | no acceleration |
| `SPAD_ENCODER_ACC`          | a single encoder with Clockwise/Counterclockwise events and accelleration      |                 |
| `SPAD_DOUBLE_ENCODER_NOACC` | a double encoder with CW/CCW events for inner and outer knob                   | no acceleration |
| `SPAD_DOUBLE_ENCODER_ACC`   | a double encoder with CW/CCW events for inner and outer knob and accelleration |                 |

### Sending encoder input updates

`8,<index>,<directionvalue>;`

#### Single Encoder

send -1 for counterclockwise turn

send 1 for clockwise turn

#### Double Encoder

Inner Encoder  `-1 / 1`

Outer Encoder `-100 / 100`
