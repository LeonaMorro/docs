.. _option_adjustRefRoot:

adjustRefRoot
^^^^^^^^^^^^^

+---------------+----------------------------------------------------------------+
| used by       | nPose V3.00 -                                                  |
+---------------+----------------------------------------------------------------+
| Script        | Slave                                                          |
+---------------+----------------------------------------------------------------+
| Data Type     | bool: 0/1                                                      |
+---------------+----------------------------------------------------------------+
| Default value | 0                                                              |
+---------------+----------------------------------------------------------------+
| Short         | Turn this on to reference adjusts to the root prim rather than |
|               | the prim the slave script is in.                               |
+---------------+----------------------------------------------------------------+

As someone might add more and more animations and notecards to their build, they
will notice it takes longer and longer for the viewer to open the edit screen.
At some point this annoyance reaches a point where it is nice to be able to move
all those animations, the slave script, and the Adjuster to one of the linked
prims just so that editing the notecards in the root allows the edit screen to
open quicker. In the past when this decision was made all adjustments to poses
would reference the prim that the slave script resided in. This would mean that
all positions would need to be re-adjusted and saved.

When the adjustRefRoot option is turned on, all the positions will reference the
root prim thus acting like the slave script had never moved. This option
removes the need to make the decision to put the slave script in a different
prim when starting the build process as it can be moved at any time without the
inconvenience of re-adjusting every pose.

Set adjustRefRoot to on will cause the root prim to be the reference for all
pose adjustments. Setting adjustRefRoot to off will cause the prim that the
slave script resides in to be the reference for all pose adjustments.
