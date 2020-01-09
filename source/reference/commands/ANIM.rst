.. _ANIM:

ANIM
^^^^

.. note::
   To use facial animations you need the `nPose Facial-Layering Plugin`_.

* ANIM is a key word used by nPose to let it know this line contains seat
  definition information.
* When nPose sees this key word it will delete all existing seat defines from
  memory and start over with the new lines to rebuild the seat defines.
* ANIM is the only key word which nPose uses to create seats in memory.
* One ANIM line within a card will define one seat being seat 1.
* Two ANIM lines within a card will define two seats, the first line being
  seat 1, and the second line being seat 2. etc.

The syntax is as follows:

* ``ANIM|animationName|positionVector|rotationVector[|facial[|seat name]]``

The syntax is written this way because there are 4 required elements (keyword,
animation, positionVector, and and rotationVector) and the other elements are
optional.

The positionVector is an offset to either the root prim or the prim that the
slave script is located in, depending on the global option :ref:`adjustRefRoot`.

A line beginning with the key word ANIM will let the core know the rest of the
line will contain information to animate and position an Avatar. More
importantly, the use of this keyword is to tell nPose to setup a seat you will
need in this pose set, multiple ANIM lines will setup multiple seats for this
pose set. Similar to the notecard names, the core is expecting to see an element
separator. In the menu names the separator is the colon but inside the notecard
the separator is the vertical bar. The information we need to give the core
within a line beginning with the key word ANIM consists of the following:

* Key word (vertical bar) animation name exactly (vertical bar) positionVector
  (vertical bar) rotationVector (vertical bar) optional any facials we want to
  run (vertical bar) optional seat name.

The animation name must match the name of the animation in the Contents tab of
the edit window. Copy/paste is the most reliable way to add the animation name.
The animation must also be in the contents of the prim.

Vectors are written as follows <0.0, 0.0, 0.0>,  three numbers separated by a
comma. <x offset, y offset, and z offset>.

Facial animations can be any of the internal animations found here:
http://wiki.secondlife.com/wiki/Internal_Animations Call them by name.
Multiple facials can be called by separating them with the tilde "~".
To add a facial expression without a seat name, simply add it after the
rotation vector as follows:

* ``ANIM|animationName|<0,0,0>|<0,0,0>|facial``

To add a seat name but no facial, the seat name is expected to follow facial
expression in this line and must be written as follows:

* ``ANIM|animationName|<0,0,0>|<0,0,0>||seat name``

If the core sees only one line in the notecard, it will setup nPose to have
only one seat and handle only one seated Avatar. Any additional Avatars who
attempt to sit will be booted off. To allow for more seats and thus more Avatars
to sit, add additional ANIM lines to the notecard with their own set of
information.
