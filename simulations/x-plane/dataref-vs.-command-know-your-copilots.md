# Dataref vs. Command: Know Your Copilots

Okay, aviator—before we start wiring buttons to things like flaps, lights, ejector seats (hey, no judgment), we need to understand the two main languages X-Plane speaks: **Datarefs** and **Commands**.

Think of these like your cockpit crew. One tells you what’s going on. The other _makes_ things happen.

#### 🎧 Datarefs: The Sim Whisperers

**Datarefs** are like the gauges and readouts in your cockpit. They **tell you the current state** of something in the sim. They’re _informational_. Want to know if the landing gear is down? There’s a dataref for that. Want to see your fuel level? Yep—dataref.

They're like saying:\
📻 _“Hey sim, what’s the current altitude of this bird?”_\
And the sim replies:\
🛩️ _“You’re at 2,700 feet, boss.”_

You **read** datarefs to get info. Some can be **written to** (we’ll get to that), but they don’t _do_ anything on their own.

`✍️`` `_`Example:`_\
`sim/cockpit2/switches/landing_lights_on = 1`\
`(This tells you the landing lights are on. Maybe. Sometimes. Depending on the aircraft. Yay, X-Plane!)`

#### 🛎️ Commands: The Doers

**Commands** are the sim’s action-takers. They **make something happen**—like flipping a switch, toggling a light, or yelling “CLEAR PROP!” before engine start (okay, maybe not that last one… yet).

They’re like saying:\
🎙️ _“Hey sim, turn on the landing lights.”_\
And the sim _does it_—no questions asked.

You don’t get a value back, you just send the command and hope the sim complies. (Most of the time, it does. Sometimes it acts like a teenager.)

`✈️`` `_`Example:`_\
`sim/lights/landing_lights_toggle`\
`(This tells the sim: “Toggle the landing lights!”)`

#### So... Which One Do I Use?

* ✅ **Use a command** when you want to make something happen. (Buttons, switches, momentary events)
* ✅ **Use a dataref** when you want to check the state of something. (LEDs, displays, conditions)
* ✅ Sometimes, use **both** if you want to change something _and_ confirm it worked.

#### 🧩 Bonus Tip: Not All Aircraft Play Nice

Some aircraft (especially custom ones) love using their own secret datarefs and commands. So if your button doesn’t seem to be doing anything, you may need to do a little detective work using **DataRefTool** to figure out what’s _actually_ going on under the hood.

That's it! You've just passed the "Datarefs vs. Commands" ground school exam. No written test required, but feel free to celebrate with a smug throttle push.
