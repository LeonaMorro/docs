.. _o_menuDist:

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
