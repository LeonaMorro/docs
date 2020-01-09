.. _PLUGINMENU:

PLUGINMENU
^^^^^^^^^^

The syntax is as follows:

* ``PLUGINMENU|pluginName|[pluginMenuParameters[|pluginActionParameters]]``

| ``pluginName``: the unique name of the plugin. Build in plugins are: npose_changeseat, npose_unsit, npose_pickseat, npose_offset
| ``pluginMenuParameters``: plugin specific parameters for menu creation
| ``pluginActionParameters``: plugin specific parameters for the action

.. note::
 If you want nPose to not remenu, please use the command ``PLUGINMENU|void``.
 (In previous versions of nPose, this had to be done by adding a "-" sign at the
 end of the button name)
