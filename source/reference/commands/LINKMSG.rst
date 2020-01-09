.. _c_LINKMSG:

LINKMSG
^^^^^^^

The syntax is as follows:

* ``LINKMSG|arbNum|message[|%AVKEY%[|pauseTime]]``

The syntax is written this way to indicate that %AVKEY% and delay time are
optional.
         
LINKMSG lines are used to pass information to scripts that are looking to act
when a specific arbNum is used. This information is intended to extend the
normal functionality of nPose in some way (many times keying a plugin to do
something).

LINKMSG lines execute as soon as they are processed from the notecard and the
line information is discarded from within nPose.

The optional %AVKEY% is used when a specific command needs to know who touched
the menu. This will grab the menu toucher's key and pass it along with the
message.  

The optional 'pauseTime' is specifically intended for use when a prop is rezzed
and that prop needs time to rez and get scripts up and running before nPose
sends a message to the prop (such as temp attach commands).

.. note::
   Try hard to not use the 'pauseTime' (it is evil), use the :ref:`c_TIMER`
   command instead.
