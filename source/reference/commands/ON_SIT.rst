.. _ON_SIT:

ON_SIT
^^^^^^

.. note::
  You need the `nPose SAT-NOTSAT Plugin`_ V3.10 or higher for this to work

The syntax is as follow:

* ``ON_SIT|seatNumber|command``

Example:
::

 ON_SIT|1|PROP|propName|<0,0,0>|<0,0,0>

rezzes the prop propName if someone sits on a particular seat.

This works like the old SATMSG but has an improved, more flexible syntax.

.. note::
   If you use ``ANIM``, ``SCHMO`` or ``SCHMOE`` and ``ON_SIT`` commands in one
   notecard make sure to write the ``ON_SIT`` commands somewhere AFTER the
   corresponding ``ANIM``, ``SCHMO`` or ``SCHMOE`` command.
