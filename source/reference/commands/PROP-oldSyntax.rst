PROP (oldSyntax)
^^^^^^^^^^^^^^^^

.. warning::
   Deprecated: use the command :ref:`PROP` instead.

.. note::
   To use this command you need the `nPose Prop Plugin`_ <=V0.10

The syntax is as follows:

* ``PROP|propName|positionVector|rotationVector[|explicit|[quiet]]``

The syntax is written this way to indicate that explicit and also quiet are
optional.

.. note::
   For nPose control of props, props must have the prop plugin within their
   contents. If not these props will stay rezzed until they are manually deleted
   by owner.

The position and rotation vectors are an offset referenced from the prim that
the core script is in. The position vector can be anywhere within a sim the
owner has permissions to build. A normal prop will live only as long as the pose
set and will be deleted.

The optional 'explicit' prop will live until explicitly told to die. The syntax
for explicit die command:

* ``PROP|propName|propName=die``

The optional 'quiet' prop will have new position reporting suppressed. This is
so that moving props do not flood local chat with information when props are
meant to move (new in V2.01).
