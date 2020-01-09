.. _PROP:

PROP
^^^^

.. note::
   To use this command you need the `nPose Prop Plugin`_ V1.00 or newer.

The syntax is as follows:

* ``PROP|propName|positionVector|rotationVector[|groupNumber|[quiet]]``

| ``propName``: string, the name of the object you want to rez.
| ``positionVector``: vector, position is an offset referenced from the prim that the core script is in. The position vector can be anywhere within a sim the owner has permissions to build.
| ``rotationVector``: vector (euler, degrees), rotation is an offset referenced from the prim that the core script is in.
| ``groupNumber``: integer (0-15), default: 0, a freely chosen number. specialty: Props with the groupNumber 0 will die whenever the default NC or a NC with an ANIM command is read.
| ``quiet``: string, prop will have new position reporting suppressed. This is so that moving props do not flood local chat with information when props are meant to move.
 
The syntax is written this way to indicate that groupNumber and also quiet are
optional.

.. note::
   For nPose control of props, props must have the prop plugin within their
   contents. If not these props will stay rezzed until they are manually deleted
   by owner.
