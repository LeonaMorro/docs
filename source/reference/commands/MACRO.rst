.. _c_MACRO:

MACRO
^^^^^

The syntax is as follows:

* ``MACRO|macroName=macroValue[|macroName=macroValue[|...]]``

Defines a macro. Macros may be used inside permissions / menu prompt / button
text / path / some menu plugins.

Example:

Imagine a bus with a drivers seat and several passenger seats. Passengers should
be able to change the seat to any other passenger seat but not to the driver
seat.

We use a macro for "grouping" the seat to a "driver" group and a passenger group
inside the ``.init`` notecard:

::

 MACRO|driver=1|passenger=2~3~4~5~6~7~8~9~10~11~12

We then create a notecard with the name ``SET:ChangeSeat{@passenger}``
(here we use the macro inside the permission to make sure that only a passenger
will see the button) and the content:

::

  MENUPLUGIN|nPose_changeSeat|@passenger

and here we use the macro as a parameter for the nPose_changeSeat plugin
