.. _TIMER:

TIMER
^^^^^

.. note::
  You need the `nPose SAT-NOTSAT Plugin`_ V3.10 or higher for this to work

The syntax is as follow:  

* ``TIMER|[(string)timerName]|(csv list)seconds|command``

| ``timerName``: case insensitive, user defined name, can be empty. More than one timer with the same name is valid. Choose a name if you want to be able to remove the timer with ``TIMER_REMOVE``.
| ``seconds``: you may supply multiple comma separated float values. Special: you may also supply a "r" followed by 2 float values to create a random value between the first and the second float value.
| ``command``: the command string

Example:
::

  TIMER|myTimer|5.5|LINKMSG|5000|The timer triggered after 5.5 seconds

sents a LINKMSG 5.5 seconds after the timer started.  

::

  TIMER|myTimer|r,300,600|LINKMSG|5000|Triggered

Triggers at a random time between 5 and 10 minutes.

::

 TIMER|myTimer|300,600,r,300,600|LINKMSG|5000|Triggered

Triggers at a random time between 5 and 10 minutes. Triggers also after
5 minutes and after 10 minutes.
