To adjust poses be sure the build includes the base scripts, the Adjuster prim, and a BTN notecard to call the Admin menu.  See [Utility Notecards](Utility Notecards) for more information on getting the Admin menu.

Find the Adjuster prim within the nPose folder contents.  This prim is a full perm vertical rectangle with painted sides.  

The Adjuster contains a special script which will report it's position back to nPose when moved.  The corresponding seat position is then updated to this new position and the notecard contents for this line is chatted to local for the owner only.  This seat position will remain until a notecard is processed by nPose.  To make this position permanent, copy the line from local and use that to replace the line in the corresponding pose set notecard.

