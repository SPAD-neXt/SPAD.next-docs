---
description: (Because Clicking With a Mouse Is So Last Flight)
---

# Basic Flight Controls - Button Setup

#### 🧭 Step 1: Select Your Device

Head over to the **left panel** in SPAD.neXt and pick the device you want to configure:

* Yoke
* Button box
* Throttle quadrant
* Or your custom-built “looks like it belongs in a spaceship” panel

If it has buttons, it’s invited to the party.<br>

Step 2: Activate the Lego Brick

Before you start pressing buttons like a caffeinated first officer, make sure the **Lego brick icon** is turned on.

This enables **input detection**, so SPAD.neXt can see what you’re pressing.

> 🧠 _If this isn’t on, you’ll be pressing buttons into the void wondering why nothing is happening. The sim equivalent of yelling “Hello?” into a dead radio._

#### 🎯 Step 3: Press the Button

Now press the button you want to configure.

SPAD.neXt will highlight and select it instantly like:\
🛫 _“Ah, Button 5… a bold choice.”_

#### ➕ Step 4: Create the Event

* Click **“Add Event”**
* Choose when it should trigger:

Options include:

* **Pressed** → when you push the button
* **Pressed (short)** → Press for less than the default time (1000 ms)
* **Pressed (long)** →  Press for longer than the default time (1000 ms)&#x20;
* **Button Held** → When you press and hold the button Options include:\
  Threshold (time when spad considers the button being held) Frequency (how often it repeats the Action being executed.
* **Released** → when you let go
* **On / Off** → for toggle switches

> ✈️ _Rule of thumb:_
>
> * Momentary button? → use **Pressed**
> * Toggle switch? → use **On/Off**

#### 🛎️ Step 5: Add an Action

Now click the **➕ (plus) icon** to add what the button actually does.

You’ve got two main flight paths here:

**🛫 Option A: Use a Command (Recommended for Most Cases)**

* Select **“Send Simulation Event”**
* Search for your command (no more file gymnastics—SPAD.neXt’s got this covered now)

Examples:

```
sim/lights/beacon_lights_toggle
sim/lights/beacon_lights_off
sim/lights/beacon_lights_on
```

Choose how it runs:

* **Execute Command Once** → quick tap (most common)
* **Begin Command / End Command** → for press-and-hold actions

> 🎯 _Commands are perfect for things like toggles, autopilot buttons, gear, lights—basically anything you’d “press” in the cockpit. Most things in X-plane are tied to commands, only use Option B when you have run out of Option A._ \
> _Note: Some Aircraft developers Do not tie cockpit buttons or switches to the default commands, nor do they tie them to Custom Commands. In this case Option B_

**📟 Option B: Use a Dataref (For Precision Work)**

* Select **“Set Dataref Value”**
* Enter your dataref
* Define the value

Example:

```
sim/cockpit2/switches/landing_lights_on = 1
```

> 🧠 _Use this when you want full control instead of “toggle and hope for the best.”_

#### 🧪 Step 6: Test It

Fire up X-Plane and press your button:

* Light turns on? ✅
* Gear drops? ✅
* Aircraft doesn’t explode? ✅

You’re good to go.

If not… well… welcome to troubleshooting. We’ve all been there.

#### 🧠 Pro Tips from the Left Seat

* 💡 Use **datarefs as conditions** to sync LEDs or states
* 🧩 Stack multiple actions if you want one button to do several things (because why not?)

#### ✈️ Final Words from the Captain

You’ve now officially moved beyond “clicking things on-screen” and into the world of **proper cockpit interaction**.

Your buttons now:

* Do what you want
* When you want
* Without mouse gymnastics
