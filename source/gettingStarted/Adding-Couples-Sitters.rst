Adding Couples Sitters
----------------------

Adding a second seat to the nPose object is very simple.  Follow these
instructions:

* In the contents of the nPose object, edit the SET:DEFAULT notecard.
* Add a second line to this notecard similar to the first. |br|
  ``ANIM|meditation|<0.0, 0.0, 0.0>|<0.0, 0.0, 0.0>``
* Save this notecard and it's ready for adjusting.

.. note::
   We are allowed to use the same animation for both seats.

When Utilities/Admin/Adjust is clicked a second Adjuster will be rezzed, one for
each sitter. Change seats to move your Avatar to this second seat. This can be
done by adding another Utility notecard to the build (found in the nPose release
folder in your inventory) called "SET:Utilities:ChangeSeat{seated}".

Edit this adjuster and move your Avatar as described before to position this
Avatar in the desired position. Copy the line in local and replace that second
line in the SET:DEFAULT notecard.

Now we have the simplest couples pose set built and ready for operation.
