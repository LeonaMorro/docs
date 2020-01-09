.. include:: ../global.rst

Commands (NC Contents)
----------------------

There are several commands (key words) that nPose is looking for when processing
lines within a notecard. Commands are always all capital letters.

.. note::
   For notes or annotations within the notecard, best practice is to begin
   these lines with the pound sign (#).


Animations
^^^^^^^^^^

+-----------------+------------------------+
|     command     | required nPose Version |
+=================+========================+
| :ref:`c_ANIM`   | 0.00 - ∞               |
+-----------------+------------------------+
| :ref:`c_SCHMO`  | 2.00 - ∞               |
+-----------------+------------------------+
| :ref:`c_SCHMOE` | 2.00 - ∞               |
+-----------------+------------------------+


Props
^^^^^

+--------------------------------------+------------------------+------------------------------------+
|               command                | required nPose Version |      additional requirements       |
+======================================+========================+====================================+
| :ref:`c_PROP`                        | 3.00 - ∞               | `nPose Prop Plugin`_ V1.00 - ∞     |
+--------------------------------------+------------------------+------------------------------------+
| :ref:`c_PROPDIE`                     | 3.00 - ∞               | `nPose Prop Plugin`_ V1.00 - ∞     |
+--------------------------------------+------------------------+------------------------------------+
| :ref:`c_PROP_oldSyntax` (deprecated) | 0.00 - 3.19            | `nPose Prop Plugin`_ V0.00 - V0.99 |
+--------------------------------------+------------------------+------------------------------------+

Events
^^^^^^

+---------------------------------+------------------------+------------------------------------------+
|             command             | required nPose Version |         additional requirements          |
+=================================+========================+==========================================+
| :ref:`c_ON_SIT`                 | 3.10 - ∞               | `nPose SAT-NOTSAT Plugin`_ V3.10 - ∞     |
+---------------------------------+------------------------+------------------------------------------+
| :ref:`c_ON_UNSIT`               | 3.10 - ∞               | `nPose SAT-NOTSAT Plugin`_ V3.10 - ∞     |
+---------------------------------+------------------------+------------------------------------------+
| :ref:`c_TIMER`                  | 3.10 - ∞               | `nPose SAT-NOTSAT Plugin`_ V3.10 - ∞     |
+---------------------------------+------------------------+------------------------------------------+
| :ref:`c_TIMER_REMOVE`           | 3.10 - ∞               | `nPose SAT-NOTSAT Plugin`_ V3.10 - ∞     |
+---------------------------------+------------------------+------------------------------------------+
| :ref:`c_SATMSG` (deprecated)    | 0.00 - 3.29            | `nPose SAT-NOTSAT Plugin`_ V0.00 - V3.29 |
+---------------------------------+------------------------+------------------------------------------+
| :ref:`c_NOTSATMSG` (deprecated) | 0.00 - 3.29            | `nPose SAT-NOTSAT Plugin`_ V0.00 - V3.29 |
+---------------------------------+------------------------+------------------------------------------+

Other
^^^^^

+----------------------+------------------------+
|       command        | required nPose Version |
+======================+========================+
| :ref:`c_DEFAULTCARD` | 3.00 - ∞               |
+----------------------+------------------------+
| :ref:`c_MENUPROMPT`  | 3.00 - ∞               |
+----------------------+------------------------+
| :ref:`c_OPTION`      | 3.00 - ∞               |
+----------------------+------------------------+
| :ref:`c_DOCARD`      | 3.10 - ∞               |
+----------------------+------------------------+
| :ref:`c_PLUGINMENU`  | 3.00 - ∞               |
+----------------------+------------------------+

Other (Advanced)
^^^^^^^^^^^^^^^^

+------------------------+------------------------+
|        command         | required nPose Version |
+========================+========================+
| :ref:`c_LINKMSG`       | 0.00  - ∞              |
+------------------------+------------------------+
| :ref:`c_PAUSE`         | 2.00 - ∞               |
+------------------------+------------------------+
| :ref:`c_UDPBOOL`       | 3.00 - ∞               |
+------------------------+------------------------+
| :ref:`c_UDPLIST`       | 3.10 - ∞               |
+------------------------+------------------------+
| :ref:`c_MACRO`         | 3.00 - ∞               |
+------------------------+------------------------+
| :ref:`c_PLUGINCOMMAND` | 3.00 - ∞               |
+------------------------+------------------------+


Commands alphabetical
---------------------

.. toctree::

   commands/ANIM
   commands/DEFAULTCARD
   commands/DOCARD
   commands/LINKMSG
   commands/MACRO
   commands/MENUPROMPT
   commands/NOTSATMSG
   commands/ON_SIT
   commands/ON_UNSIT
   commands/OPTION
   commands/PAUSE
   commands/PLUGINCOMMAND
   commands/PLUGINMENU
   commands/PROP-oldSyntax
   commands/PROP
   commands/PROPDIE
   commands/SATMSG
   commands/SCHMO-and-SCHMOE
   commands/TIMER
   commands/TIMER_REMOVE
   commands/UDPBOOL
   commands/UDPLIST
