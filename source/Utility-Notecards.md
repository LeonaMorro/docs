There is a collection of utility notecards which support some vital and optional features of nPose.  The list of provided utility notecards are listed below:

|Utility |Description|Contents|
|--------|-----------|--------|
|`BTN:Utility:Admin-{owner}`|This notecard contains a LINKMSG to tell nPose to bring up the Admin menu|`LINKMSG\|-888\|admin\|%AVKEY%`|
|`BTN:Utility:ChangeSeat-`|This notecard contains a LINKMSG to tell nPose to bring up a menu with available seats|`LINKMSG\|-888\|ChangeSeat\|%AVKEY%`|
|`BTN:Utilities:Swap1-2`|This notecard contains a LINKMSG to tell nPose to swap the sitters in seats 1 and 2|`LINKMSG\|202\|1,2\|%AVKEY%`|
|`BTN:Utility:Sync`|This notecard contains a LINKMSG to tell nPose to sync all animations for the seated Avatars|`LINKMSG\|-888\|sync\|%AVKEY%`|
|`BTN:Utility:Offsets-`|This notecard contains a LINKMSG to tell nPose to pull the Offsets menu|`LINKMSG\|-888\|offset\|%AVKEY%`|
|`BTN:Utilities:UsedMemory`|This notecard contains a LINKMSG to tell all scripts to report their used memory stats|`LINKMSG\|34334\|\|%AVKEY%`|

These notecard names are not fixed and can be changed at the builders' desire and menu path.  The contents are required to initiate their function.

These notecards are not required and can be omitted at the builders' desire.  For example: If a build will only have two sitters, then the Swap button is useful and the ChangeSeats button would be far less useful and can be omitted.