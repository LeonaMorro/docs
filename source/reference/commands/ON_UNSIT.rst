.. _c_ON_UNSIT:

ON_UNSIT
^^^^^^^^

.. note::
  You need the `nPose SAT-NOTSAT Plugin`_ V3.10 or higher for this to work

The syntax is as follow:

* ``ON_UNSIT|seatNumber|command``

Example:

::

  ON_UNSIT|1|PROPDIE

removes all props if someone leaves a particular seat.

This works like the old NOTSATMSG but has an improved, more flexible syntax.

.. note::
   If you use ``ANIM``, ``SCHMO`` or ``SCHMOE`` and ``ON_UNSIT`` commands in one
   notecard make sure to write the ``ON_UNSIT`` commands somewhere AFTER the
   corresponding ``ANIM``, ``SCHMO`` or ``SCHMOE`` command.
