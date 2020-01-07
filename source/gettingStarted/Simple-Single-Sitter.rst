Simple Single Sitter
--------------------

To make the most simple object animate an Avatar when seated, rez this object
in world and add the following items from nPose release to the contents, found
in the nPose Release 3.0 distribution:

* object: Adjuster
* script: nPose Core
* script: nPose Dialog
* script: nPose Menu
* script: nPose NC Reader
* script: nPose Slave
* notecard: .init
* notecard: SET:DEFAULTCARD
* notecard: SET:Utilities:Admin:Adjust
* notecard: SET:Utilities:Admin:PosDump
* notecard: SET:Utilities:Admin:StopAdjust
* notecard: SET:Utilities:Admin{owner}

Once this is done the object will function with a menu. Click the object and a
dialog menu will pop up on your viewer screen.  We cannot sit our object however.
We will need to add a couple more things to allow us to sit.

Pick a single animation from your inventory to be used to animate a sitter and
add it to the contents of the object. For the purpose of this document, I will
use the animation named "meditation".  If you don't have this animation, any
that you have in your inventory will work.

One more item is needed to complete the nPose object and allow an Avatar to sit
and use "meditate". Open the SET:DEFAULTCARD notecard and add a line to tell
nPose which animation and where to position our Avatar:

:code:`ANIM|meditation|<0.0, 0.0, 0.0>|<0.0, 0.0, 0.0>`

Save this notecard and reset the scripts so that nPose scripts will read the
.init notecard and load the SET:DEFAULTCARD.  See more about the .init notecard
here: :ref:`nc-names`.

Now this object will be functional and anyone can sit this object.

To discover what nPose is now capable of, click for menu and see a button named
"DEFAULTCARD" derived from the notecard name we just added the line above in.
We also see the "Utilities" button derived from the notecards we originally
added to the object contents.

It is possible that the position of our Avatar is correct but not likely. The
following notes will tell you how to adjust the position and rotation of the
seated Avatar:

* Click the nPose object for menu.
* Select "Utilities" from the menu which appears on your viewer screen.
* Select "Admin" from the menu which appears next on your viewer screen.
* Select "Adjust" from the menu which appears next on your viewer screen.

An Adjuster will be rezzed right where you are seated. Edit and move this
adjuster to the position which best suits your needs. The Avatar seated on the
nPose object will move to match the new position and information will be sent to
your local chat which will look like the line we added to the SET:DEFAULTCARD
notecard. Each time the Adjuster is moved, a new line of information will be
sent to local.

When the seated Avatar is in a position that suits your needs, copy the last
line from local and replace the line in the SET:DEFAULTCARD notecard for
permanent adjustments to be used.

This completes the nPose setup for a single sitter who is animated with
"meditation" animation.

To expand this nPose object and add more pose sets, add another animation to the
nPose object and create another SET type notecard to drive this animation and
follow the same instructions to add the contents as described above. Add this
notecard to the same nPose object and you will see another button when clicking
for menu to select this pose.
