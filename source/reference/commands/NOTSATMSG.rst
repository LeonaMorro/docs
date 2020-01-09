.. _c_NOTSATMSG:

NOTSATMSG
^^^^^^^^^

.. warning::
   Deprecated: use the command :ref:`c_ON_UNSIT` instead.

.. note::
  You need the `nPose SAT-NOTSAT Plugin`_ for this to work

The syntax is as follows:

* ``NOTSATMSG|arbNum|message[|id[|seat#]]``

NOTSATMSG lines are exactly the same as SATMSG lines with the exception that
NOTSAGMSG lines run when someone is no long in that particular seat or the pose
set is changed.

There are now two ways to associate a particular NOTSATMSG with a particular seat.

1. Place the SATMSG just below the ANIM line that the NOTSATMSG should be
   associated with.  There is no need to use the 'optional' seat# this way.
2. Add the 'optional' seat# at the end of the NOTSATMSG line. This will tell nPose
   which seat to associate the NOTSATMSG with. If NOTSATMSG lines are needed with
   SCHMOE/SCHMO lines, the 'optional' seat# becomes 'required'. If the
   'optional' seat# is used, they can be placed in any order within the notecard.
