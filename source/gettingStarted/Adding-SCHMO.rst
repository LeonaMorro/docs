Adding SCHMO
------------

SCHMO allows us to modify a seat in memory from a notecard.  The seats must
already be setup with ANIM lines, then nPose will modify the seat for the menu
user only.

SCHMO works for single sitter modifications. All seats can have a SCHMO line in
a single notecard but only the menu user will change.

For example we can use the following notecard for our SET:Meditate notecard:

::

  ANIM|meditation|<0.704, 0.685, 0.8>|<0.0, 0.0, -135.0>
  ANIM|meditation|<-0.753, 0.736, 0.8>|<0.0, 0.0, -45.0>
  ANIM|meditation|<-0.737, -0.711, 0.8>|<0.0, 0.0, 45.0>
  ANIM|meditation|<0.704, -0.711, 0.8>|<0.0, 0.0, 135.0>


We can then add a second notecard by the name of SET:Stories and add the
following lines:

::

  SCHMO|1|npose-storyteller|<0.704, 0.685, 0.8>|<0.0, 0.0, -135.0>
  SCHMO|2|npose-storyteller|<-0.753, 0.736, 0.8>|<0.0, 0.0, -45.0>
  SCHMO|3|npose-storyteller|<-0.737, -0.711, 0.8>|<0.0, 0.0, 45.0>
  SCHMO|4|npose-storyteller|<0.704, -0.711, 0.8>|<0.0, 0.0, 135.0>

When the sitter in seat4 clicks the "Stories" menu button only that sitter will
change poses.
