.. _TIMER_REMOVE:

TIMER_REMOVE
^^^^^^^^^^^^

.. note::
  You need the `nPose SAT-NOTSAT Plugin`_ V3.10 or higher for this to work

The syntax is as follow:

* ``TIMER_REMOVE[|(csv list)Names]``

``Names``: a list of comma separated, case insensitive timer names which should
be removed. A wildcard ``*`` is allowed at the end of each name. If you do not
provide the NameList or the NameList contains the name ``*`` then all timers
will be removed.

Example:

::

  TIMER_REMOVE
  TIMER_REMOVE|*
  TIMER_REMOVE|whatever,*

this commands will remove all timers

::

  TIMER_REMOVE|redApple

removes the timer with the name "redApple"  

::

  TIMER_REMOVE|redApple, green*

removes the timer with the name "redApple" and also all timers with a name
beginning with "green"
