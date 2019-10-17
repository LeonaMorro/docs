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