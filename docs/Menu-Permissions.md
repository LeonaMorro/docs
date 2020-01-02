Menu Permissions are one of a few options that can be set for nPose to control globally how nPose reacts in certain situations.  For a more on these global options, see [Setting Global Options](Setting Global Options).

Menu permissions control who can pull a menu on first click.  There are three options to pick from when setting Menu Permissions:

| Option    | Action                     |
|-----------|---------------------------------|
| `Public`    | Everyone who clicks gets menu   |
| `Group`     | Only group members get menu     |
| `<other>`   | Only the object owner gets menu   |

### Setting Menu Permissions
Menu Permissions cannot be set from within the menu.  This must be set by a LINKMSG within any nPose notecard.  Menu Permissions will be changed when the LINKMSG is processed.

Syntax for setting Menu Permissions:
`LINKMSG|-240|permit=<option>`

By default, the menu script will automatically set the Menu Permissions to "Public".  If this is the desired Action, the LINKMSG is not required.  Also by default the build owner will always be able to pull the nPose menu when it is clicked.

If Menu Permissions are set to "Group", then the menu requester must activate the same group that nPose is set to pull the nPose menu.

If Menu Permissions are set to anything other than Public or Group, the menu script will not recognize this permission and (by default) only the build owner will have access to pull the nPose menu.

**Adding the LINKMSG to set Menu Permissions in this default notecard will ensure that nPose sets the Menu Permissions upon reset.  See [Menu System](Menu System) for more information on the default pose set.**

### Build Menu Permissions into the menu:
When a build would function better where the owner has the ability to change the Menu Permissions from the menu, it can be done as follows:
Make 3 notecards using similar names and these contents:

| Name | Contents |
|-----------|---------------------------------|
|BTN:Utilities:Permits:Owner{Owner}|`LINKMSG|-240|permit=Owner`|
|BTN:Utilities:Permits:Group{Owner}|`LINKMSG|-240|permit=Group`|
|BTN:Utilities:Permits:Public{Owner}|`LINKMSG|-240|permit=Public`|

Add these notecards to the build and now the owner will have the ability to change permissions from the nPose menu.

### Checking Current Menu Permissions setting:
The menu does offer a way to check what the Menu Permissions are currently set to.  Navigate to the Admin submenu and click the Options button.  Within the header of this menu the owner will see what all of the current option settings are set to.