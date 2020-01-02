Getting started
===============

Simple Single Sitter
--------------------
This document assumes that you have a basic understanding of editing and adjusting objects in world.
This document also assumes that you have unpacked nPose Release and can be found in your inventory.  If not, the latest release can be found either on marketplace for free or at nPose HQ.

To make the most simple object animate an Avatar when seated, rez this object in world and add the following items from nPose release to the contents, found in the nPose Release 2.0 distribution:
* Adjuster
* nPose Core
* nPose Dialog
* nPose Menu
* nPose NC Reader
* nPose SAT/NOTSAT handle
* nPose Slave
* BTN:Utilities:Admin-{owner}

Once this is done the object will function with a menu.  Click the object and a dialog menu will pop up on your viewer screen.  We cannot sit our object however.  We will need to add a couple more things to allow us to sit.

Pick a single animation from your inventory to be used to animate a sitter and add it to the contents of the object.  For the purpose of this document, I will use the animation named "meditation".  If you don't have this animation, any that you have in your inventory will work.

One more item is needed to complete the nPose object and allow an Avatar to sit and use "meditate".  In inventory make a new notecard and name it SET:Meditate.  Open this notecard and add a line to tell nPose which animation and where to position our Avatar:

`ANIM|meditation|<0.0, 0.0, 0.0>|<0.0, 0.0, 0.0>`

Save this notecard and add it to the contents of the object.

Now this object will be functional and anyone can sit this object.

To discover what nPose is now capable of, click for menu and see a button named "Meditate" derived from the notecard name we just added.  We also see the "Utilities" button derived from the notecard we originally added to the object contents.

It is possible that the position of our Avatar is correct but not likely.  The following notes will tell you how to adjust the position and rotation of the seated Avatar:
* Click the nPose object for menu.
* Select "Utilities" from the menu which appears on your viewer screen.
* Select "Admin" from the menu which appears next on your viewer screen.
* Select "Adjust" from the menu which appears next on your viewer screen.

An Adjuster will be rezzed right where you are seated.  Edit and move this adjuster to the position which best suits your needs.  The Avatar seated on the nPose object will move to match the new position and information will be sent to your local chat which will look like the line we added to the SET:Meditate notecard.  Each time the Adjuster is moved, a new line of information will be sent to local.

When the seated Avatar is in a position that suits your needs, copy the last line from local and replace the line in the SET:Meditate notecard for permanent adjustments to be used.

This completes the nPose setup for a single sitter who is animated with "meditation" animation.

To expand this nPose object and add more pose sets, add another animation to the nPose object and create another SET type notecard to drive this animation and follow the same instructions to add the contents as described above.  Add this notecard to the same nPose object and you will see another button when clicking for menu to select this pose.

Adding Couples Sitters
----------------------
Adding a second seat to the nPose object is very simple.  Follow these instructions:
* In the contents of the nPose object, edit the SET:Meditate notecard.
* Add a second line to this notecard similar to the first.
`  ANIM|meditation|<0.0, 0.0, 0.0>|<0.0, 0.0, 0.0>`
* Save this notecard and it's ready for adjusting.

**_(We are allowed to use the same animation for both seats.)_**

When Utilities/Admin/Adjust is clicked a second Adjuster will be rezzed, one for each sitter.
Change seats to move your Avatar to this second seat.  This can be done by adding another Utility notecard to the build (found in the nPose release folder in your inventory) called "BTN:Utilities:ChangeSeat-".

Edit this adjuster and move your Avatar as described before to position this Avatar in the desired position.
Copy the line in local and replace that second line in the SET:Meditate notecard.

Now we have the simplest couples pose set built and ready for operation.

Adding SCHMO
------------

SCHMO allows us to modify a seat in memory from a notecard.  The seats must already be setup with a normal SET type notecard with ANIM lines, then nPose will modify the seat for the menu user only.

SCHMO works for single sitter modifications.  All seats can have a SCHMO line in a single notecard but only the menu user will change.

For example we can use the following notecard for our DEFAULT:Meditate notecard:

  `ANIM|meditation|<0.70354, 0.68508, 0.80000>|<0.00001, 0.00000, -135.00040>|`

  `ANIM|meditation|<-0.75256, 0.73643, 0.80000>|<0.00001, 0.00000, -44.99962>|`

  `ANIM|meditation|<-0.73697, -0.71104, 0.80000>|<0.00001, 0.00000, 44.99962>|`

  `ANIM|meditation|<0.70354, -0.71104, 0.80000>|<0.00001, 0.00000, 135.00040>|`

We can then add a second notecard by the name of SET:Stories and add the following lines:

  `SCHMO|1|npose-storyteller|<0.70354, 0.68508, 0.80000>|<0.00001, 0.00000, -135.00040>|`

  `SCHMO|2|npose-storyteller|<-0.75256, 0.73643, 0.80000>|<0.00001, 0.00000, -44.99962>|`

  `SCHMO|3|npose-storyteller|<-0.73697, -0.71104, 0.80000>|<0.00001, 0.00000, 44.99962>|`

  `SCHMO|4|npose-storyteller|<0.70354, -0.71104, 0.80000>|<0.00001, 0.00000, 135.00040>|`

When the sitter in seat4 clicks the "Stories" menu button only that sitter will change poses.

