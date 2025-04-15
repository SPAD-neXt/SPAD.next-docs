---
description: (Where We Tame the Yoke, Wrangle the Rudder, and Throttle Like a Pro)
---

# Basic Flight Controls – Axis Setup

Now it’s time to tackle the real beasts of the flight deck—**your flight control axes.**\
Because if your yoke is limp, your rudder’s confused, and your throttle’s spiky… you're flying a flying brick with cool lights.

#### ✈️ What Is an Axis?

Think of axes (plural of axis, not something you swing at your PC) as the analog controls—smooth, continuous inputs like:

* Yoke pitch & roll (your classic “push and pull” and “left and right”)
* Rudder pedals (tail wagging)
* Throttle(s) (moar power!)
* Mixture, Prop pitch, toe brakes, spoilers, flaps, coffee temperature knobs (okay maybe not that last one… yet)

If it moves smoothly and _isn’t_ a button, it’s probably an axis.

### X-plane Default Axes + Datarefs + Value Ranges

<table data-header-hidden><thead><tr><th width="154"></th><th width="189"></th><th width="180"></th><th valign="top"></th></tr></thead><tbody><tr><td><strong>Axis Role</strong></td><td><strong>What It Controls</strong></td><td><strong>Default DataRef</strong></td><td valign="top"><strong>Value Range</strong></td></tr><tr><td><code>Pitch</code></td><td>Elevator (yoke push/pull)</td><td><code>sim/joystick/yoke_pitch_ratio</code></td><td valign="top"><code>-1.0</code> (nose down) to <code>1.0</code> (nose up)</td></tr><tr><td><code>Roll</code></td><td>Ailerons (yoke left/right)</td><td><code>sim/joystick/yoke_roll_ratio</code></td><td valign="top"><code>-1.0</code> (left) to <code>1.0</code> (right)</td></tr><tr><td><code>Yaw</code></td><td>Rudder (pedals or stick twist)</td><td><code>sim/joystick/yoke_heading_ratio</code></td><td valign="top"><code>-1.0</code> (left) to <code>1.0</code> (right)</td></tr><tr><td><code>Throttle 1</code></td><td>Engine power (engine 1)</td><td><code>sim/flightmodel/engine/ENGN_thro[0]</code></td><td valign="top"><code>0.0</code> (idle) to <code>1.0</code> (full power)</td></tr><tr><td><code>Throttle 2</code></td><td>Throttle (engine 2)</td><td><code>sim/flightmodel/engine/ENGN_thro[1]</code></td><td valign="top"><code>0.0</code> to <code>1.0</code></td></tr><tr><td><code>Throttle 3</code>, <code>4</code></td><td>More throttles</td><td><code>ENGN_thro[2]</code>, <code>[3]</code></td><td valign="top"><code>0.0</code> to <code>1.0</code></td></tr><tr><td><code>Prop 1</code></td><td>Prop RPM (engine 1)</td><td><code>sim/flightmodel/engine/ENGN_prop[0]</code></td><td valign="top"><code>0.0</code> (low RPM) to <code>1.0</code> (high RPM)</td></tr><tr><td><code>Prop 2</code></td><td>Prop RPM (engine 2)</td><td><code>ENGN_prop[1]</code></td><td valign="top"><code>0.0</code> to <code>1.0</code></td></tr><tr><td><code>Mixture 1</code></td><td>Fuel/air mix (engine 1)</td><td><code>sim/flightmodel/engine/ENGN_mixt[0]</code></td><td valign="top"><code>0.0</code> (cutoff) to <code>1.0</code> (full rich)</td></tr><tr><td><code>Mixture 2</code></td><td>Mixture (engine 2)</td><td><code>ENGN_mixt[1]</code></td><td valign="top"><code>0.0</code> to <code>1.0</code></td></tr><tr><td><code>Speedbrake</code></td><td>Spoilers / airbrakes</td><td><code>sim/flightmodel/controls/speedbrake_ratio</code></td><td valign="top"><code>0.0</code> (retracted) to <code>1.0</code> (full out)</td></tr><tr><td><code>Flaps</code></td><td>Flap lever</td><td><code>sim/flightmodel/controls/flap_ratio</code></td><td valign="top"><code>0.0</code> (up) to <code>1.0</code> (full flaps)</td></tr><tr><td><code>Reverse Thrust</code></td><td>Reversers active (per engine)</td><td><code>sim/flightmodel/engine/ENGN_thro_use_rev</code></td><td valign="top"><code>0</code> (off) or <code>1</code> (on)</td></tr><tr><td><code>Brakes</code></td><td>Main brakes (left/right combined or split)</td><td><code>sim/flightmodel/controls/parkbrake</code> or <code>l_brake_add</code> / <code>r_brake_add</code></td><td valign="top"><code>0.0</code> (released) to <code>1.0</code> (full brake)</td></tr><tr><td><code>Nosewheel Steering</code></td><td>Nose gear steering</td><td><code>sim/flightmodel/controls/nwheel_steer</code></td><td valign="top"><code>-1.0</code> (left) to <code>1.0</code> (right)</td></tr><tr><td><code>Landing Gear</code></td><td>Gear handle (if used as axis)</td><td><code>sim/flightmodel/controls/gear_handle_down</code></td><td valign="top"><code>0</code> (up) or <code>1</code> (down)</td></tr></tbody></table>

**🎮 Step 1: Axis Configuration**

* On the **left panel**, click the device you want to configure (like your yoke, throttle quadrant, pedals).
* Head to the **“Axis” tab**.
* You’ll see a list of all your available axis inputs. If it wiggles, it’ll show up here.
* **move the axis** you want to configure (wiggle that stick!).&#x20;

**✍️**

**🎚️**

**💾**

***
