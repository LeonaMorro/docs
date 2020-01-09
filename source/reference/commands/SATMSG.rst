.. _SATMSG:

SATMSG
^^^^^^

.. warning::
   Deprecated: use the command :ref:`ON_SIT` instead.

.. note::
  You need the `nPose SAT-NOTSAT Plugin`_ for this to work

The syntax is as follows:

* ``SATMSG|arbNum|message[|id[|seat#]]``

SATMSG lines are intended to do much the same work as a LINKMSG except they
don't execute until someone sits a particular seat. SATMSG processing will
automatically grab the sitter's key and pass it with the message.

There are now two ways to associate a particular SATMSG with a particular seat.

1. Place the SATMSG just below the ANIM line that the SATMSG should be
   associated with.  There is no need to use the 'optional' seat# this way.
2. Add the 'optional' seat# at the end of the SATMSG line. This will tell nPose
   which seat to associate the SATMSG with. If SATMSG lines are needed with
   SCHMOE/SCHMO lines, the 'optional' seat# becomes 'required'. If the
   'optional' seat# is used, they can be placed in any order within the notecard.
