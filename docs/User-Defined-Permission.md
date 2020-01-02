User Defined Permissions (UDP) is an extension of the [[Button Permissions]], which allows all scripts to register their own button permissions which are than handled by the menu script.
To do so, the menu have to know 3 things:

1. the Name of the UDP
2. the Type of the UDP
3. the Value of the UDP

These three have to be send as a Comma Separated List to the menu script with the corresponding link Message:

```lsl
integer USER_PERMISSION_UPDATE = -806;
string UDP_NAME="*** the name ***";
string UDP_TYPE="*** the type ***";
string udpValue="*** the value ***"; //must not contain a ","
llMessageLinked(LINK_SET, USER_PERMISSION_UPDATE, llList2CSV([UDP_NAME, UDP_TYPE, udpValue]), NULL_KEY);
```
Every time the `udpValue` changes, this linkMessage has to be send.

Syntax of the string part of the linkmessage:  
`UDP_NAME1, UDP_TYPE1, udpValue1[, UDP_NAME2, UDP_TYPE2, udpValue2[, ...]]`

## UDP Name
The name is chosen by you. It has to be unique. Therefore we maintain a list with registered UDP names ([[UDP Register]]).
If you want to use UDP for your own purpose (don't want to give your scripts away) you should prefix your UDP name with `my`. UDP names with the `my`prefix don't need to be registered.

## UDP types and values
Currently there are 2 types of User Defined Permissions, a `bool` type and a `list` type.

### UDP type `bool`
The `bool` type expects a simple boolean value as the `udpValue`: 

`0: FALSE`  
all other values`: TRUE`

Using this type allows you to simply switch on/off menu buttons.

### UDP type `list`
The `list` type expects a list of Avatar UUIDs (concentrated into a string) as the `udpValue`. You may use any seperator except "," (colon). If the UUID of the Avatar using the menu is inside this "list", the corresponding UDP is evaluated as `TRUE` (the button is shown).

## Examples
There are two example scripts inside the nPose plugins folder:

### `nPose DayNight Plugin`
This shows you the use of the `bool` type. You may also find it here:  
[[https://github.com/LeonaMorro/nPose-DayNight-plugin]]

### `nPose AccessControlList Plugin`
This shows you the use of the `list` type (and also the use of the new NC Reader). You may also find it here:  
[[https://github.com/LeonaMorro/nPose-AccessControlList-plugin]]
