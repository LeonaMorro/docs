.. _o_2default:

2default
^^^^^^^^

+---------------+------------------------------------------------------------------+
| used by       | nPose V0.00 - ∞                                                  |
+---------------+------------------------------------------------------------------+
| Script        | Core                                                             |
+---------------+------------------------------------------------------------------+
| Data Type     | bool: 0/1                                                        |
+---------------+------------------------------------------------------------------+
| Default value | 0                                                                |
+---------------+------------------------------------------------------------------+
| Short         | Change to default pose when all sitters stand or menu times out. |
+---------------+------------------------------------------------------------------+

When 2default is set to 1 nPose will work differently in two ways:

* When all sitters stand, nPose will return to and automatically select the
  default pose set (as defined in the .init NC).  This returns nPose to a known
  first state and ready for a new session of sitters.
* When used as a rezzer for props with no sitters, nPose will return to the
  default pose set (as defined in the .init NC) after 60 seconds of no menu
  activity.  If no props are rezzed from the default pose set, nPose basically
  cleans house and removes all rezzed props.
