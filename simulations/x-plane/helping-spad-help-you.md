---
description: That Command File
---

# Helping Spad Help You

Good news, Captain! SPAD.neXt is pretty clever when it comes to finding datarefs inside X-Plane. It can sniff them out on its own, so we don’t need to mess with the drt\_last\_run\_datarefs.txt file anymore. That one can stay in the hangar.\
But when it comes to commands, SPAD.neXt still needs a little hand-holding—think of it like your co-pilot before coffee. \
\
drt\_last\_run\_commandrefs.txt\


In order for SPAD.neXt to actually recognize and use the commands from that file, we need to give it a proper callsign. That means renaming it to:\
**commands.txt**

🧩 Pro Tip:\
If you don’t see the .txt at the end—trust me, it’s still there. Windows likes to play hide and seek with file extensions. Just rename the file to commands (don’t add .txt yourself), and it’ll work like a charm.\
&#x20;                                                                   **No mayday required.**

📁 Now Boarding: Your Aircraft Folder\
Here’s the important part—once you’ve renamed the file, drag and drop that commands.txt file into the folder for the specific aircraft you're setting up. That’s the one with the .acf file inside—you know, the aircraft’s brain. Think of it like loading the flight plan into the correct FMS. Wrong plane, wrong commands, wrong day.\
Once it’s in place, SPAD.neXt will be able to read those custom commands for that aircraft, and you’ll be all set for takeoff!

**Clearing the Runway: Editing Your commands.txt File**\
Alright, we’re almost there, but before we take off, there’s a little bit of housecleaning to do. SPAD.neXt is a seasoned pro—it already knows all the standard X-Plane commands (think of them as the "universal airline rules" that every aircraft follows). So, we don’t need to clutter our flight plan with them. We’re going to clear those out and just leave the custom commands that are specific to your setup.\
Here’s how to do it:

**🧹 Step 1: Open commands.txt**\
Personally I use notepad++ It MUST be a plain text editor.\
Grab that commands.txt file you just dropped into your aircraft folder and open it up. You’ll see a list of commands that looks a lot like a checklist—but be warned, some of those items are repeats. Think of it like a flight manual with a few too many pages.

\
**🗑️ Step 2: Remove the Standard X-Plane Commands**\
Now here’s where we lighten the load. All the standard X-Plane commands start with: \
&#x20;                                                                                   **sim/**\
These can be safely removed, no questions asked. SPAD.neXt already knows these commands by heart, so we don’t need them in the file. Go ahead and delete any line that begins with sim/—it’s like clearing out the unnecessary weight before we hit the runway.

\
**🛠️ Step 3: Keep Everything Else (But Leave Two Blank Lines at the Top)**\
Everything else that remains in the file should stay, as it’s likely your custom commands or unique settings. But here’s the key part: make sure there are two blank lines at the very top of the file. It’s like a runway clearance before the action begins—just a little extra space to make everything run smoothly.

\
&#xNAN;**✂️ Step 4: Save and Close**\
Once you’ve cleared out the standard commands, saved everything you want to keep, and made sure those two blank lines are at the top, save the file and close it up. Now, when SPAD.neXt loads up, it’ll only care about the custom commands you've set, making the whole process faster and cleaner.
