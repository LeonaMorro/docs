Setting Global Options
----------------------

There are some options to set up how nPose will react in certain situations.
These Options are mostly global settings and once they are set will rarely need
to be changed for a specific nPose build. You can set this global option from
within any Notecard (best practice: set the from within the .init Notecard) with
the command

``OPTION|optionName=optionValue[|optionName=optionValue[...]]``

The list of nPose global options are here below:

+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
|         Option         | nPose Version |     Setting      | Default |                                                                      Short Description                                                                      |
+========================+===============+==================+=========+=============================================================================================================================================================+
| 2default_              | 0.xx? - ∞     | bool: 0/1        | 0       | Change to default pose when all sitters stand or menu times out                                                                                             |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| adjustRefRoot_         | 3.00 - ∞      | bool: 0/1        | 0       | Turn this on to reference adjusts to the root prim rather than the prim the slave script is in.                                                             |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| autoLanguage_          | 3.10 - ∞      | bool: 0/1        | 1       | enables the automatic language selection. Disable it for language debugging purposes                                                                        |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| defaultLanguagePrefix_ | 3.10 - ∞      | string           | SET     | for debugging purposes you may set it to a 2 letter language code                                                                                           |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| dialogBackward_        | 3.00 - ∞      | bool: 0/1        | 0       | enables a backward button inside a multi paged menu                                                                                                         |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| dialogTimeout_         | 3.00 - ∞      | integer: seconds | 120     | If a menu user is not sitting on the nPose Object, the Menu will timeout after the specified number of seconds                                              |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| enableEvents_          | 3.00 - ∞      | integer: Mask    | 0       | See script `nPose SAT-NOTSAT Plugin`                                                                                                                        |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| facialExp_             | 0.xx? - ∞     | bool: 0/1        | 1       | Global on/off of facials for all sitters                                                                                                                    |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| menuDist_              | 2.00? - ∞     | float: meters    | 30.0    | Maximum distance from the nPose build click for menu is allowed                                                                                             |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| menuOnSit_             | 0.xx? - ∞     | bool: 0/1        | 0       | Menu pops up automatically for each sitter when they first sit                                                                                              |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| quietAdjusters_        | 3.00 - ∞      | bool: 0/1        | 0       | Turn this on to quiet new position reporting by the adjusters, and also adjuster reporting when clicked. PosDump will still report all positions/rotations. |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| seatAssignList_        | 3.10 - ∞      | list of CSV      | a       | with this list you can define which seat a new sitter gets                                                                                                  |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
| useDisplayNames_       | 3.00 - ∞      | bool: 0/1        | 1       | Turn this on to see sitter's display name in ChangeSeats menu.                                                                                              |
+------------------------+---------------+------------------+---------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+


2default
^^^^^^^^

When 2default is set to 1 nPose will work differently in two ways:

* When all sitters stand, nPose will return to and automatically select the default pose set (as defined in the .init NC).  This returns nPose to a known first state and ready for a new session of sitters.
* When used as a rezzer for props with no sitters, nPose will return to the default pose set (as defined in the .init NC) after 60 seconds of no menu activity.  If no props are rezzed from the default pose set, nPose basically cleans house and removes all rezzed props.

menuOnSit
^^^^^^^^^

When menuOnSit is set to 1 nPose will work differently as follows:
* Each new sitter will be presented the nPose menu when they first sit.

facialExp
^^^^^^^^^

When facialExp is set to 1 nPose will work differently as follows:
* All sitters for all pose sets with facial expressions set up will be enabled.

menuDist
^^^^^^^^

This option sets the maximum distance an Avatar can be away from the nPose build and still receive the menu when clicked.
* This distance is the magnitude of the vector difference between the build position and the Avatar position.
* This distance is only calculated when the build is clicked for menu and has no effect if the menu is already active.

The owner of the object allways gets a menu.

useDisplayNames
^^^^^^^^^^^^^^^

When useDisplayNames is turned on, the change seats menu will display the users' display name on the button associated with the seat they occupy. Unoccupied seats will display Seat#.

adjustRefRoot
^^^^^^^^^^^^^

As someone might add more and more animations and notecards to their build, they will notice it takes longer and longer for the viewer to open the edit screen.  At some point this annoyance reaches a point where it is nice to be able to move all those animations, the slave script, and the Adjuster to one of the linked prims just so that editing the notecards in the root allows the edit screen to open quicker.  In the past when this decision was made all adjustments to poses would reference the prim that the slave script resided in.  This would mean that all positions would need to be re-adjusted and saved.
When the adjustRefRoot option is turned on, all the positions will reference the root prim thus acting like the slave script had never moved.  This option removes the need to make the decision to put the slave script in a different prim when starting the build process as it can be moved at any time without the inconvenience of re-adjusting every pose.
Set adjustRefRoot to on will cause the root prim to be the reference for all pose adjustments. Setting adjustRefRoot to off will cause the prim that the slave script resides in to be the reference for all pose adjustments.

quietAdjusters
^^^^^^^^^^^^^^

Like the above option, quietAdjusters option is one of those options I think is very valuable.  Consider when adjusting a couples set.  First adjust position for one sitter, then change seats to the other and adjust that position.  If quietAdjusters is turned off, local chat is spammed by a line each time the adjuster is moved.  It becomes a difficult task to copy the correct line to paste into the notecard at the correct place.  In the end, it becomes much more convenient to click Pose Dump and get all the positions within the card at once (in the right order) for copy/paste.  This alone makes it much nicer to turn on quietAdjusters and not be confused about which line is the one needed.  Consider adjusting the positions in 4 notecards before saving them, with quietAdjusters turned off finding the correct line for each card would be almost impossible, but with quietAdjusters adjusters turned on and clicking Pose Dump when finished with each card then there are only 4 dumps in local to pick from.

enableEvents
^^^^^^^^^^^^

dialogTimeout
^^^^^^^^^^^^^

dialogBackward
^^^^^^^^^^^^^^

seatAssignList
^^^^^^^^^^^^^^

A comma separate list consisting of integer values (seat numbers) and one character keywords.
- `a` means ascending
- `d` means descending
- `r` means random
- any integer is a seat number

If someone want to sit on a nPose object (without numbered seats), nPose descides on which seat the new sitter is placed. By default new sitters are placed on the free seat with the lowest seat number. If you set `seatAssignList=d` a new sitter will be placed on the free seat with the highest seat number. If you set `seatAssignList=r` a seat will be randomly choosen. You can also add more values to the list, for example `seatAssignList=1,5,r` which means: If seat 1 is free then place a new sitter on seat 1, if not then try seat 5. If seat 5 is also occupied then choose a ramdom seat.

autoLanguage
^^^^^^^^^^^^

defaultLanguagePrefix
^^^^^^^^^^^^^^^^^^^^^
