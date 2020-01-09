.. _SCHMO:

SCHMO
^^^^^

.. _SCHMOE:

SCHMOE
^^^^^^

.. note::
   To use facial animations you need the `nPose Facial-Layering Plugin`_.

This changes the animation of a single sitter (SCHMO) or group of sitters
(SCHMOE) without affecting any of the other sitters. SCHMO/SCHMOE lines cannot
build a seat, they can only modify existing seat defines. This allows us to
selectively modify seat defines while not modifying all. We are required to tell
nPose which seat each lines is intended to modify.

.. note::
   This does not build a pose set, it only changes a pose set already built
   using the keyword 'anim'.

The syntax is as follows:

*  ``SCHMO|seat#|animation|positionVector|rotationVector[|facial|[seat name]]``
*  ``SCHMOE|seat#|animation|positionVector|rotationVector[|facial|[seat name]]``

| ``seat#`` = number value of the seat to be replaced.
| ``animation`` = inventory name of animation
| ``positionVector`` = postion relative to the nPose object (depending on the global option :ref:`adjustRefRoot`.)
| ``rotationVector`` = rotation (Euler/degree) relative to the nPose object
| ``facial`` = any of the built in expressions found here: http://wiki.secondlife.com/wiki/Internal_Animations
| ``seat name`` = How the seat is named in the change seat menu if no one is sitting in that spot
         
* SCHMO lines can only be run when requested from the menu and requires a menu
  user's key.
* SCHMOE lines are free from the menu user restriction and can be run from a
  plug-in or other such source.
* When multiple SCHMO lines are in the same notecard, only the menu user's seats
  will change.
* When multiple SCHMOE lines are in the same notecard, all these seats will
  change.
