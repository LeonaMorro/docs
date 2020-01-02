The menu is made from notecard names that begin with three specific key words.  Each key word denotes something a bit different to nPose but the all make up the menu.  Begin notecard name with one of the key words (depending on the purpose), followed by a colon as separator, and menu button name at the end.  All notecards within the build beginning with these key words will be used to create menu buttons.

The three key words are as follows:

|Key Word |Description |
|---------|------------|
|[SET](#SET) |nPose will expect this notecard type to contain information about animating seated Avatars |
|[DEFAULT](#DEFAULT) |nPose will treat this notecard type the same as a SET type except this will be the default pose used |
|[BTN](#BTN) |nPose will not expect information about animations but instead will handle props and pass messages as needed |

### SET
The SET type notecard has a very important roll for nPose.  The SET type notecard is what nPose uses to build the available seats for sitters via the [NC Contents](NC Contents).  The nPose system will remove all seats and begin building new seats within the script using [ANIM](NC Contents#ANIM) lines inside the notecard.

For the purposes of the menu system, nPose does not look inside the notecard and only concerns itself with the notecard name.  To test this, make a notecard in your inventory and give it this name "SET:Meditate".  Put this notecard into a prim with the basic set of nPose scripts and touch the prim to get it's menu.  The menu should display one button with the word "Meditate" on it.  Please note that clicking this button will cause a script error because nPose is expecting something inside the notecard which will be discussed here: [ANIM](NC Contents#ANIM).

### DEFAULT
To begin discussing this topic it is important to know that when nPose is setting itself up, it will grab the very first SET type notecard it finds in the build contents (top down) and use this first SET notecard for the default pose (initial pose set).  In some cases this pose set is not desirable as the initial pose set so nPose has the DEFAULT type notecard to use instead.

The DEFAULT type notecard follows all the rules of a SET type notecard except this single pose set will be used as the initial pose set.  If more than one DEFAULT type notecard is used in the contents, unexpected results will occur. For the expected results, only include one DEFAULT type notecard in any one build.

### BTN
The BTN type notecards allow the build to do many things which do not require building a set of seats while creating a menu button to be used and call some of these things.  The nPose system will not process lines that begin with ANIM, all other contents will be processed.  See [NC Contents](NC Contents) for a more in depth idea of what is possible for BTN type notecards.

### Menu Order
Setting the order of buttons is now built into nPose.  Simply add a notecard by the name of '.Change Menu Order' and add it to the contents tab of nPose.  This name is coded into the scripts and cannot be anything different from the mentioned name.  With this notecard added, nPose will build the menu based upon the contents of this notecard so be sure to add all the SET, BTN, and DEFAULT notecard names to the contents of this '.Change Menu Order' notecard.  nPose also knows not to sort the menu before it is displayed when using this '.Change Menu Order' notecard.  Add and arrange the SET, BTN, and DEFAULT notecard names in the order they will be displayed to the user.

I have experimented with setting submenu buttons and found an easy way to arrange them in any order desired.  At the top of the '.Change Menu Order' notecard, add a listing of submenu buttons in the order they will be displayed, and then add sub-submenu buttons next, etc. While setting up the submenu order, it is not required to have a button name while building the menu, nPose will reserve the submenu place when simply using the submenu menu path, such as BTN:Utilities will reserve this submenu path and desired order for the Utility submenu button.  Then in a group below, add all the Utility buttons (with button names) and put them in the specific order within that group desired.  

nPose will not process empty lines and specifically lines beginning with the hash '#' so grouping submenu items and making notes within while you go is easy to do.

IMPORTANT: PLEASE REMEMBER THAT ANY NOTECARDS NOT LISTED IN THE '.Change Menu Order' NOTECARD WILL NOT BE SHOWN IN YOUR MENU.

### Extra Notes
In some cases it is not desirable to have nPose re-menu, such as when a notecard contents tells nPose to pull a different menu either built in or from a plugin.  Telling nPose not to re-menu is very easy.  Simply add a minus at the end of the button name in the notecard name (SET:Meditate-).

There are cases where it does not make sense for some sitters to see specific menu buttons.  The nPose system allows us to limit who can see and use these specific buttons using [Button Permissions](Button Permissions).


