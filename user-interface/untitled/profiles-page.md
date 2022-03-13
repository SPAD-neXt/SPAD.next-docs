---
description: This section describes the layout and use of the Profiles Menu Page
---

# Profiles Page

When the Profiles Menu Page is selected on the Left Side Navigation Column the UI will look similar to Fig 1.  This is where you create configuration profiles that you can then Link to Aircraft in your simulations.  The current Active Profile will already be selected and you will see the Red SPAD.neXt plane to the left as well.  If you select another Profile the Highlight will change but the Red Plane will stay next to the Active Profile.

![](<../../.gitbook/assets/image (4).png>)Fig 1

The Sub Tab Navigation is on the Left side like other Menus.  The First Three Menus (called out in Fig 2) will be present.  Additional Navigation will be available when you create Profiles that have a "\\" in the name to instruct SPAD.neXt to create sub directories for sorting them.  As seen here there is a MSFS directory that was created (this will be further explained as you continue to read)\
\
![](<../../.gitbook/assets/image (7).png>)Fig 2

The Three Sub Navigation sections are My Profiles (kind of like the "root directory" of profile storage that is found in your Documents example C:\Users\User\Documents\SPAD.neXt\profiles). If no sub folders are created by the user then all Profile XML files will be located there.\
\
Online Profiles (Fig 3) will display all of the available Online Profiles that have been published and your license has entitlements for (note that any published profile AFTER the expiry of an Update Subscription will not be available).  Called out in Fig 3 is the filtering criteria and ability to search for Profiles as well.

![](<../../.gitbook/assets/image (8).png>)Fig 3\
\
My Published Profiles Will display the Profiles that you have published to the Online System and have shared with the community. Fig 4 displays an example of what you published menu could look like.  Note that again the Filters at the bottom can also be used.

![](<../../.gitbook/assets/image (9).png>)Fig 4

In the case of Fig 5 where we have the example of a sub directory for MSFS it can be seen that the name of the Profile was edited to have MSFS\ added to the front of it.  This instructs SPAD.neXt to create a subfolder of that name in your profiles directory and then place the profile in that location.  Note: You may need to restart SPAD.neXt after creating a new directory that was not present before launch.

![](<../../.gitbook/assets/image (15).png>)Fig 5

When we look at Fig 6 and it's Callout you will see that the Right Side of the UI is actions regarding the Profiles.  When Actions are not available they will be "greyed" out and can not be selected.  In Fig 6 we see that since no profile is Highlighted in the MSFS subdirectory that we are viewing then it is not possible to perform any actions other than "Create Empty Profile" which will start a totally new and blank profile with nothing assigned to your devices.  The other Action is "Open Profiles Folder" which will launch Explorer and take you to the Folder or "Sub Folder" that you are currently viewing.

![](<../../.gitbook/assets/image (10).png>)Fig 6

If we Highlight the Profile in the MSFS directory that we are currently viewing we can see that all of the right hand side Profiles actions become selectable (see Fig 7).  The Top two actions are straight forward.\
\
Activate Profile will Make the Highlighted Profile load it's configuration of devices.  Note if you had another Profile open that was edited it should prompt you to save...  However it is always good to manually press the Save icon first to be safe\
\
Delete Profile is the other pretty straight forward action that will allow you to delete the Profile entirely ...  Hey maybe you made a new version from an old profile and now that you are happy with your changes you are ready to clean up the old stuff...

![](<../../.gitbook/assets/image (12).png>)Fig 7

Moving on to the Next Action Item "Edit Profile" in Fig 8.  This will open an additional Dialog Box that allows you to modify or "Edit" the selected Profile.  Keep in mind that you do not need to activate a profile to use this editor.  This is not about Editing the Devices but rather the Properties of this Profile.\
\
When the edit dialog opens up you are now able to Modify the Profile name (here you see how it is in a sub folder and removing that MSFS\ would move it back to the root profiles folder).\
\
Version numbers can be edited manually.  As you make changes and edit the profile the versions will automatically increment.  here you can change them yourself. \
\
Description section allows you to write up all the details and information that you would like about this profile.  The more you put into this the more others can read about it if you are to publish this to the online system.

![](<../../.gitbook/assets/image (6).png>) Fig 8

The next selection in the "Edit Profile" Action is found on the Bottom and will open up another dialog that will allow you to edit the Aircraft that you want assigned to this profile.  Note that in Fig 9 this instance of SPAD.neXt is operating on the "networked" mode and is only able to see the list of the current active plane.  Local installations that are run on the same machine will see additional Aircraft.\
\
Select the Aircraft on the Left Side that you want to link to this profile and then press the Arrow to "transfer" them to the assigned aircraft on the Right hand side.  If you want to remove an aircraft you can select them on the Right Side and use the Left Arrow to remove them from the assignments Field.  Note: If you were editing a Profile and add an aircraft that is already assigned in another profile you will be warned that making the assignment will remove it from the other Profile.  Once finished press Save to confirm the assignments.

![](<../../.gitbook/assets/image (2).png>)Fig 9

Continuing on with the Edit Actions is the Device Assignments operation (Fig 10) which will launch another dialog that lists all of the device configurations that were saved with this profile and which physically connected devices they are assigned too.  This can also help with re-mapping incase a duplicate device that only get instantiated by windows was out of order...  Once complete click OK

![](../../.gitbook/assets/image.png)Fig 10

Moving on to the next Action item "Aircraft Assignments" in Fig 11 we see that there are quick selects that effectively take you to the same editor for the Aircraft Assignments as we saw in the Edit Profile section.  This is no different in operation however saves the button click of going into Edit Profile first when you just need to link a new Aircraft

![](<../../.gitbook/assets/image (13).png>)Fig 11

"Device Assignments" (Fig 12) is an action item which also has the quick navigation and does not required editing the Profile to bring up the dialog editor.

![](<../../.gitbook/assets/image (5) (1).png>)Fig 12

"Publish Profile" action will bring up the Dialog to allow you to share the entire Profile to the online community.  In Fig 13 we see what this context menu looks like and that it allows you to pick which devices are included with the publish and which aircraft if you want to help filter it for very specific single or multiple different planes.

![](<../../.gitbook/assets/image (3).png>)Fig 13

The 7th Action Item is the "New Profile from this" which will allow you to create a new profile but based on all of the device configurations that you have created in this profile.  Effectively another term would be Cloning the profile.  As seen in Fig 14 when this is selected you are prompted with having to enter a new Name for this profile.  This is a helpful way to take a profile that is setup perfect for one plane but needs a couple of tweaks to work well with another....  ie the C172 G1000 just needs some different switch assignments than say the DA-40 with the G1000.

![](<../../.gitbook/assets/image (14).png>)Fig 14

The Last Action is "Convert Profile".  This will take older version of the profile an convert them to the new version.  This will result in a backup being created in your directory.  Note that if you activate an Old Profile that needs to be converted you will be prompted to do that anyway.
