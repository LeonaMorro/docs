There are some options to set up how nPose will react in certain situations.  These Options are mostly global settings and once they are set will rarely need to be changed for a specific nPose build.  The list of nPose options are here below:

| Option | Setting | Default | Description |
|--------|---------|---------|-------------|
|[2default](#2default)| on/off  | off | Change to default pose when all sitters stand or menu times out |
|[menuonsit](#menuonsit)|on/off  | off | Menu pops up automatically for each sitter when they first sit|
|[sit2getmenu](#sit2getmenu)|on/off| off | No menu comes up when clicking the build while standing |
|[facialExp](#facialExp)| on/off  | on | Global on/off of facials for all sitters |
|[menudist](#menudist)| (float)meters  | 30.0 | Maximum distance from the nPose build click for menu is allowed |
|[permit](#permit)  | Public, Group, Owner | Public | Global control for menu when someone clicks the build for menu |

Syntax for Options:
`LINKMSG|-240|option=value[~option=value]`
The system will accept several single entry lines or a tilde delimited list of entries all in one line.
### 2default:
When 2default is set to 'on' nPose will work differently in two ways:
* When all sitters stand, nPose will return to and automatically select the DEFAULT pose set.  This returns nPose to a known first state and ready for a new session of sitters.
* When used as a rezzer for props with no sitters, nPose will return to the DEFAULT pose set after 60 seconds of no menu activity.  If no props are rezzed from the DEFAULT pose set, nPose basically cleans house and removes all rezzed props.

### menuonsit:
When menuonsit is set to 'on' nPose will work differently as follows:
* Each new sitter will be presented the nPose menu when they first sit.

### sit2getmenu:
When sit2getmenu is set to 'on' nPose will work differently as follows:
* All users must be seated to get a menu except for the owner.  The owner can get the menu while standing as well.

### facialExp:
When facialExp is set to 'on' nPose will work differently as follows:
* All sitters for all pose sets with facial expressions set up will be enabled.

### menudist:
This option sets the maximum distance an Avatar can be away from the nPose build and still receive the menu when clicked.
* This distance is the magnitude of the vector difference between the build position and the Avatar position.
* This distance is only calculated when the build is clicked for menu and has no effect if the menu is already active.

### permit:
This option sets up the [Menu Permissions](Menu Permissions) for the build and determines which group of users can ever get a menu when clicked.

[Button Permissions](Button Permissions) are applied after this global permit is set.  This means that after a user is qualified to get the menu, some menu buttons may not be displayed for use depending on how each of the [Button Permissions](Button Permissions) are set.
