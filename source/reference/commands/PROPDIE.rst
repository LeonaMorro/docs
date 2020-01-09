.. _PROPDIE:

PROPDIE
^^^^^^^

.. note::
   To use this command you need the `nPose Prop Plugin`_ V1.00 or newer.

The syntax is as follows:

* ``PROPDIE[|propNamesList[|propGroupsList]]``

| ``propNamesList``: a comma separated list of names. You may use the asterisk as a wildcard. If you don't provide a propNamesList, all props are targeted
| ``propGroupsList``: a comma separated list of group numbers. If you don't provide a propGroupsList, all propGroups are targeted

A prop will die if its name AND group matches.

Examples:
::

  PROPDIE
  PROPDIE|*
  PROPDIE|*|*

All three are equal: All Props will die.

::

  PROPDIE|Red*,GreenApple

All props with a name beginning with "Red" (RedApple, RedTomato, ...) and
additionally the "GreenApple" will die

::

  PROPDIE|*|1,2

All props that are rezzed with the group number 1 or 2 will die.

.. note::
   Please keep in mind that props rezzed with the group number 0 will also die
   whenever the default NC or a NC with an ANIM command is read.
