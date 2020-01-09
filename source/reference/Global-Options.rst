.. _globalOptions:

Global Options
--------------

There are some options to set up how nPose will react in certain situations.
These Options are mostly global settings and once they are set will rarely need
to be changed for a specific nPose build. You can set this global option from
within any Notecard (best practice: set the from within the .init Notecard) with
the :ref:`OPTION` command.

.. toctree::
   :hidden:

   options/2default
   options/adjustRefRoot



autoLanguage
^^^^^^^^^^^^

+---------------+----------------------------------------------------------+
| used by       | nPose V3.10 - ∞                                          |
+---------------+----------------------------------------------------------+
| Script        | Menu                                                     |
+---------------+----------------------------------------------------------+
| Data Type     | bool: 0/1                                                |
+---------------+----------------------------------------------------------+
| Default value | 1                                                        |
+---------------+----------------------------------------------------------+
| Short         | Enables the automatic language selection. Disable it for |
|               | language debugging purposes.                             |
+---------------+----------------------------------------------------------+


defaultLanguagePrefix
^^^^^^^^^^^^^^^^^^^^^

+---------------+--------------------------------------------------------------------+
| used by       | nPose V3.10 - ∞                                                    |
+---------------+--------------------------------------------------------------------+
| Script        | Menu                                                               |
+---------------+--------------------------------------------------------------------+
| Data Type     | string                                                             |
+---------------+--------------------------------------------------------------------+
| Default value | SET                                                                |
+---------------+--------------------------------------------------------------------+
| Short         | For debugging purposes you may set it to a 2 letter language code. |
+---------------+--------------------------------------------------------------------+

dialogBackward
^^^^^^^^^^^^^^

+---------------+------------------------------------------------------+
| used by       | nPose V3.00 - ∞                                      |
+---------------+------------------------------------------------------+
| Script        | Menu                                                 |
+---------------+------------------------------------------------------+
| Data Type     | bool: 0/1                                            |
+---------------+------------------------------------------------------+
| Default value | 0                                                    |
+---------------+------------------------------------------------------+
| Short         | Enables a backward button inside a multi paged menu. |
+---------------+------------------------------------------------------+

dialogTimeout
^^^^^^^^^^^^^

+---------------+-------------------------------------------------------------+
| used by       | nPose V3.00 - ∞                                             |
+---------------+-------------------------------------------------------------+
| Script        | Menu                                                        |
+---------------+-------------------------------------------------------------+
| Data Type     | integer: seconds                                            |
+---------------+-------------------------------------------------------------+
| Default value | 120                                                         |
+---------------+-------------------------------------------------------------+
| Short         | If a menu user is not sitting on the nPose Object, the Menu |
|               | will timeout after the specified number of seconds.         |
+---------------+-------------------------------------------------------------+

enableEvents
^^^^^^^^^^^^

+---------------+-------------------------------------------------------------+
| used by       | `nPose SAT-NOTSAT Plugin`_ V3.00 - ∞                        |
+---------------+-------------------------------------------------------------+
| Script        | nPose SAT-NOTSAT Plugin                                     |
+---------------+-------------------------------------------------------------+
| Data Type     | integer: Mask                                               |
+---------------+-------------------------------------------------------------+
| Default value | 0                                                           |
+---------------+-------------------------------------------------------------+
| Short         | If a menu user is not sitting on the nPose Object, the Menu |
|               | will timeout after the specified number of seconds.         |
+---------------+-------------------------------------------------------------+

facialExp
^^^^^^^^^

+---------------+-------------------------------------------+
| used by       | `nPose Facial-Layering Plugin`_ V3.00 - ∞ |
+---------------+-------------------------------------------+
| Script        | nPose Facial-Layering Plugin              |
+---------------+-------------------------------------------+
| Data Type     | bool: 0/1                                 |
+---------------+-------------------------------------------+
| Default value | 1                                         |
+---------------+-------------------------------------------+
| Short         | Global on/off of facials for all sitters. |
+---------------+-------------------------------------------+

When facialExp is set to 1 nPose will work differently as follows:

* All sitters for all pose sets with facial expressions set up will be enabled.

menuDist
^^^^^^^^

+---------------+------------------------------------------------------------------+
| used by       | nPose V2.00 - ∞                                                  |
+---------------+------------------------------------------------------------------+
| Script        | Menu                                                             |
+---------------+------------------------------------------------------------------+
| Data Type     | float: meters                                                    |
+---------------+------------------------------------------------------------------+
| Default value | 30.0                                                             |
+---------------+------------------------------------------------------------------+
| Short         | Maximum distance from the nPose build click for menu is allowed. |
+---------------+------------------------------------------------------------------+

This option sets the maximum distance an Avatar can be away from the nPose build
and still receive the menu when clicked.

* This distance is the magnitude of the vector difference between the build
  position and the Avatar position.
* This distance is only calculated when the build is clicked for menu and has no
  effect if the menu is already active.

The owner of the object allways gets a menu.

menuOnSit
^^^^^^^^^

+---------------+-----------------------------------------------------------------+
| used by       | nPose V0.00 - ∞                                                 |
+---------------+-----------------------------------------------------------------+
| Script        | Core                                                            |
+---------------+-----------------------------------------------------------------+
| Data Type     | bool: 0/1                                                       |
+---------------+-----------------------------------------------------------------+
| Default value | 0                                                               |
+---------------+-----------------------------------------------------------------+
| Short         | Menu pops up automatically for each sitter when they first sit. |
+---------------+-----------------------------------------------------------------+

When menuOnSit is set to 1 nPose will work differently as follows:

* Each new sitter will be presented the nPose menu when they first sit.

quietAdjusters
^^^^^^^^^^^^^^

+---------------+----------------------------------------------------------------+
| used by       | nPose V3.00 - ∞                                                |
+---------------+----------------------------------------------------------------+
| Script        | Slave, Adjuster                                                |
+---------------+----------------------------------------------------------------+
| Data Type     | bool: 0/1                                                      |
+---------------+----------------------------------------------------------------+
| Default value | 0                                                              |
+---------------+----------------------------------------------------------------+
| Short         | Turn this on to quiet new position reporting by the adjusters, |
|               | and also adjuster reporting when clicked. PosDump will still   |
|               | report all positions/rotations.                                |
+---------------+----------------------------------------------------------------+

Like the above option, quietAdjusters option is one of those options I think is
very valuable. Consider when adjusting a couples set. First adjust position for
one sitter, then change seats to the other and adjust that position. If
quietAdjusters is turned off, local chat is spammed by a line each time the
adjuster is moved. It becomes a difficult task to copy the correct line to paste
into the notecard at the correct place. In the end, it becomes much more
convenient to click Pose Dump and get all the positions within the card at once
(in the right order) for copy/paste. This alone makes it much nicer to turn on
quietAdjusters and not be confused about which line is the one needed. Consider
adjusting the positions in 4 notecards before saving them, with quietAdjusters
turned off finding the correct line for each card would be almost impossible,
but with quietAdjusters adjusters turned on and clicking Pose Dump when finished
with each card then there are only 4 dumps in local to pick from.

seatAssignList
^^^^^^^^^^^^^^

+---------------+-------------------------------------------------------------+
| used by       | nPose V3.10 - ∞                                             |
+---------------+-------------------------------------------------------------+
| Script        | Core                                                        |
+---------------+-------------------------------------------------------------+
| Data Type     | list of CSV                                                 |
+---------------+-------------------------------------------------------------+
| Default value | a                                                           |
+---------------+-------------------------------------------------------------+
| Short         | With this list you can define which seat a new sitter gets. |
+---------------+-------------------------------------------------------------+


A comma separate list consisting of integer values (seat numbers) and one
character keywords.

- `a` means ascending
- `d` means descending
- `r` means random
- any integer is a seat number

If someone want to sit on a nPose object (without numbered seats), nPose
descides on which seat the new sitter is placed. By default new sitters are
placed on the free seat with the lowest seat number. If you set 
``seatAssignList=d`` a new sitter will be placed on the free seat with the
highest seat number. If you set ``seatAssignList=r`` a seat will be randomly
choosen. You can also add more values to the list, for example
``seatAssignList=1,5,r`` which means: If seat 1 is free then place a new sitter
on seat 1, if not then try seat 5. If seat 5 is also occupied then choose a
ramdom seat.

useDisplayNames
^^^^^^^^^^^^^^^

+---------------+----------------------------------------------------------------+
| used by       | nPose V3.00 - ∞                                                |
+---------------+----------------------------------------------------------------+
| Script        | Menu                                                           |
+---------------+----------------------------------------------------------------+
| Data Type     | bool: 0/1                                                      |
+---------------+----------------------------------------------------------------+
| Default value | 1                                                              |
+---------------+----------------------------------------------------------------+
| Short         | Turn this on to see sitter’s display name in ChangeSeats menu. |
+---------------+----------------------------------------------------------------+

When useDisplayNames is turned on, the change seats menu will display the users'
display name on the button associated with the seat they occupy. Unoccupied
seats will display Seat#.

