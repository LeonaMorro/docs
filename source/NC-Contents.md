There are several key words that nPose is looking for when processing lines within a notecard.  These key words are as follows:
* [ANIM](#anim)
* [SCHMO](#schmo-and-schmoe)
* [SCHMOE](#schmo-and-schmoe)
* [PROP](#prop)
* [LINKMSG](#linkmsg)
* [PAUSE](#pause)
* [SATMSG](#satmsg)
* [NOTSATMSG](#notsatmsg)

Key words are always all capital letters.

_NOTE:  FOR NOTES OR ANNOTATIONS WITHIN THE NOTECARD, BEST PRACTICE IS TO BEGIN THESE LINES WITH THE POUND SIGN (#).  DOING THIS WILL HELP NPOSE TO RUN FASTER._

### ANIM
The syntax is as follows:
* `ANIM|animation|<0,0,0>|<0,0,0>[|facial[|seat name]]`

The syntax is written this way because there are 4 required elements (keyword, animation, position vector, and and rotation vector) and the other elements are optional.

1. _NOTE:  ANIM lines are only supported within DEFAULT and SET notecard types.  They will not be processed from within a BTN type notecard._
2. _NOTE:  SET and DEFAULT notecard types will process lines with any and all of the above listed keywords._

The position vector is an offset to the prim that the slave script is located in.
A line beginning with the key word ANIM will let the core know the rest of the line will contain information to animate and position an Avatar.  More importantly, the use of this keyword is to tell nPose to setup all the seats you will need in this pose set.  Similar to the notecard names, the core is expecting to see an element separator.  In the menu names the separator is the colon but inside the notecard the separator is the vertical bar.  The information we need to give the core within a line beginning with the key word ANIM consists of the following:
* Key word (vertical bar) animation name exactly (vertical bar) position vector (vertical bar) rotation vector (vertical bar) optional any facials we want to run (vertical bar) optional seat name.

The animation name must match the name of the animation in the Contents tab of the edit window.  Copy/paste is the most reliable way to add the animation name.  The animation must also be in the contents of the prim.

The position and rotation vectors are an offset to the position and rotation of the prim the slave script is in.  Vectors are written as follows <0.0,0.0,0.0>,  three numbers separated by a comma. <x offset, y offset, and z offset>.

Facial animations can be any of the internal animations found here: http://wiki.secondlife.com/wiki/Internal_Animations  Call them by name.  Multiple facials can be called by separating them with the tilde "~".

If the core sees only one line in the notecard, it will setup nPose to have only one seat and handle only one seated Avatar.  Any additional Avatars who attempt to sit will be booted off.  To allow for more seats and thus more Avatars to sit, add additional ANIM lines to the notecard with their own set of information.

_NOTE:  The facials and seat names are optional.  They do not have to be included for the rest to work._

[TOP](NC Contents)

### SCHMO AND SCHMOE
This changes the animation of a single sitter (SCHMO) or group of sitters (SCHMOE) without affecting any of the other sitters.

_NOTE:  THIS DOES NOT BUILD A POSE SET, IT ONLY CHANGES A POSE SET ALREADY BUILT USING THE KEYWORD 'ANIM'._

 The syntax is as follows:
*  `SCHMO|seat#|animation|<0,0,0>|<0,0,0>[|facial|[seat name]]`
*  `SCHMOE|seat#|animation|<0,0,0>|<0,0,0>[|facial|[seat name]]`


 seat# = number value of the seat to be replaced.  
 animation = inventory name of animation  
 seat name = How the seat is named in the change seat menu if no one is sitting in that spot
         
Since this function only replaces seats and does not add them there should be a DEFAULT: set defining the amount of seats available.
*  SCHMO lines can only be run when requested from the menu and requires a menu user's key.
*  SCHMOE lines are free from the menu user restriction and can be run from a plug-in or other such source.
*  When multiple SCHMO lines are in the same notecard, only the menu user's seats will change.
*  When multiple SCHMOE lines are in the same notecard, all these seats will change.

[TOP](NC Contents)

### PROP
The syntax is as follows:
* `PROP|propName|<0,0,0>|<0,0,0>[|explicit|[quiet]]`

The syntax is written this way to indicate that explicit and also quiet are optional.

_NOTE: For nPose control of props, props must have the prop plugin within their contents.  If not these props will stay rezzed until they are manually deleted by owner._

The position and rotation vectors are an offset referenced from the prim that the core script is in.  The position vector can be anywhere within a sim the owner has permissions to build.  A normal prop will live only as long as the pose set and will be deleted.
The optional 'explicit' prop will live until explicitly told to die.
The syntax for explicit die command:
* `PROP|propName|propName=die`

The optional 'quiet' prop will have new position reporting suppressed. This is so that moving props do not flood local chat with information when props are meant to move (new in V2.01).

[TOP](NC Contents)

### LINKMSG
The syntax is as follows:
* `LINKMSG|arbNum|message[|%AVKEY%[|pauseTime]]`

The syntax is werittne this way to indicate that %AVKEY% and delay time are optional.
         
LINKMSG lines are used to pass information to scripts that are looking to act when a specific arbNum is used.  This information is intended to extend the normal functionality of nPose in some way (many times keying a plugin to do something.
LINKMSG lines execute as soon as they are processed from the notecard and the line information is discarded from within nPose.
The optional %AVKEY% is used when a specific command needs to know who touched the menu.  This will grab the menu toucher's key and pass it along with the message. 
The optional 'pauseTime' is specifically intended for use when a prop is rezzed and that prop needs time to rez and get scripts up and running before nPose send the message (such as temp attach commands).  No other functions will be delayed if this LINKMSG is the last line in the notecard.

[TOP](NC Contents)

### PAUSE
The syntax is as follow:
* `PAUSE|pauseTime`

This pause is more of a global pause and will halt nPose execution of the remaining items within the notecard for the duration of the pauseTime.

[TOP](NC Contents)

### SATMSG
The syntax is as follows:
* `SATMSG|arbNum|message[|id[|seat#]]`

SATMSG lines are intended to do much the same work as a LINKMSG except they don't execute until someone sits a particular seat.  SATMSG processing will automatically grab the sitter's key and pass it with the message.
There are now two ways to associate a particular SATMSG with a particular seat.

1. Place the SATMSG just below the ANIM line that the SATMSG should be associated with.  There is no need to use the 'optional' seat# this way.
2. Add the 'optional' seat# at the end of the SATMSG line.  This will tell nPose which seat to associate the SATMSG with.  If SATMSG lines are needed with SCHMOE/SCHMO lines, the 'optional' seat# becomes 'required'. If the 'optional' seat# is used, they can be placed in any order within the notecard.

[TOP](NC Contents)

### NOTSATMSG
The syntax is as follows:
* `NOTSATMSG|arbNum|message[|id[|seat#]]`

NOTSATMSG lines are exactly the same as SATMSG lines with the exception that NOTSAGMSG lines run when someone is no long in that particular seat or the pose set is changed.

NOTE:  SATMSG and NOTSATMSG lines can now be used in BTN type notecards as long as the 'optional' seat# is used.  nPose needs this seat# information to correctly associate them with a particular seat.