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

+---------------+------------------------+
|    command    | required nPose Version |
+===============+========================+
| :ref:`ANIM`   | 0.00 - ∞               |
+---------------+------------------------+
| :ref:`SCHMO`  | 2.00 - ∞               |
+---------------+------------------------+
| :ref:`SCHMOE` | 2.00 - ∞               |
+---------------+------------------------+


Props
^^^^^

+----------------------------------+------------------------+------------------------------------+
|             command              | required nPose Version |      additional requirements       |
+==================================+========================+====================================+
| :ref:`PROP`                      | 3.00 - ∞               | `nPose Prop Plugin`_ V1.00 - ∞     |
+----------------------------------+------------------------+------------------------------------+
| :ref:`PROPDIE`                   | 3.00 - ∞               | `nPose Prop Plugin`_ V1.00 - ∞     |
+----------------------------------+------------------------+------------------------------------+
| `PROP (oldSyntax)`_ (deprecated) | 0.00 - 3.19            | `nPose Prop Plugin`_ V0.00 - V0.99 |
+----------------------------------+------------------------+------------------------------------+

Events
^^^^^^

+-------------------------------+------------------------+------------------------------------------+
|            command            | required nPose Version |         additional requirements          |
+===============================+========================+==========================================+
| :ref:`ON_SIT`                 | 3.10 - ∞               | `nPose SAT-NOTSAT Plugin`_ V3.10 - ∞     |
+-------------------------------+------------------------+------------------------------------------+
| :ref:`ON_UNSIT`               | 3.10 - ∞               | `nPose SAT-NOTSAT Plugin`_ V3.10 - ∞     |
+-------------------------------+------------------------+------------------------------------------+
| :ref:`TIMER`                  | 3.10 - ∞               | `nPose SAT-NOTSAT Plugin`_ V3.10 - ∞     |
+-------------------------------+------------------------+------------------------------------------+
| :ref:`TIMER_REMOVE`           | 3.10 - ∞               | `nPose SAT-NOTSAT Plugin`_ V3.10 - ∞     |
+-------------------------------+------------------------+------------------------------------------+
| :ref:`SATMSG` (deprecated)    | 0.00 - 3.29            | `nPose SAT-NOTSAT Plugin`_ V0.00 - V3.29 |
+-------------------------------+------------------------+------------------------------------------+
| :ref:`NOTSATMSG` (deprecated) | 0.00 - 3.29            | `nPose SAT-NOTSAT Plugin`_ V0.00 - V3.29 |
+-------------------------------+------------------------+------------------------------------------+

Other
^^^^^

+--------------------+------------------------+
|      command       | required nPose Version |
+====================+========================+
| :ref:`DEFAULTCARD` | 3.00 - ∞               |
+--------------------+------------------------+
| :ref:`MENUPROMPT`  | 3.00 - ∞               |
+--------------------+------------------------+
| :ref:`OPTION`      | 3.00 - ∞               |
+--------------------+------------------------+
| :ref:`DOCARD`      | 3.10 - ∞               |
+--------------------+------------------------+
| :ref:`PLUGINMENU`  | 3.00 - ∞               |
+--------------------+------------------------+

Other (Advanced)
^^^^^^^^^^^^^^^^

+----------------------+------------------------+
|       command        | required nPose Version |
+======================+========================+
| :ref:`LINKMSG`       | 0.xx? - ∞              |
+----------------------+------------------------+
| :ref:`PAUSE`         | 2.00 - ∞               |
+----------------------+------------------------+
| :ref:`UDPBOOL`       | 3.00 - ∞               |
+----------------------+------------------------+
| :ref:`UDPLIST`       | 3.10 - ∞               |
+----------------------+------------------------+
| :ref:`MACRO`         | 3.00 - ∞               |
+----------------------+------------------------+
| :ref:`PLUGINCOMMAND` | 3.00 - ∞               |
+----------------------+------------------------+


Commands description
--------------------

.. include:: commands/ANIM.rst
.. include:: commands/DEFAULTCARD.rst
.. include:: commands/DOCARD.rst
.. include:: commands/LINKMSG.rst
.. include:: commands/MACRO.rst
.. include:: commands/MENUPROMPT.rst
.. include:: commands/NOTSATMSG.rst
.. include:: commands/ON_SIT.rst
.. include:: commands/ON_UNSIT.rst
.. include:: commands/OPTION.rst
.. include:: commands/PAUSE.rst
.. include:: commands/PLUGINCOMMAND.rst
.. include:: commands/PLUGINMENU.rst
.. include:: commands/PROP-oldSyntax.rst
.. include:: commands/PROP.rst
.. include:: commands/PROPDIE.rst
.. include:: commands/SATMSG.rst
.. include:: commands/SCHMO-and-SCHMOE.rst
.. include:: commands/TIMER.rst
.. include:: commands/TIMER_REMOVE.rst
.. include:: commands/UDPBOOL.rst
.. include:: commands/UDPLIST.rst
