.. _o_seatAssignList:

seatAssignList
^^^^^^^^^^^^^^

+---------------+-------------------------------------------------------------+
| used by       | nPose V3.10 - ∞                                             |
+---------------+-------------------------------------------------------------+
| Script        | Core                                                        |
+---------------+-------------------------------------------------------------+
| Data Type     | list of CSV                                                 |
+---------------+-------------------------------------------------------------+
| Default value | a                                                           |
+---------------+-------------------------------------------------------------+
| Short         | With this list you can define which seat a new sitter gets. |
+---------------+-------------------------------------------------------------+


A comma separate list consisting of integer values (seat numbers) and one
character keywords.

- `a` means ascending
- `d` means descending
- `r` means random
- any integer is a seat number

If someone want to sit on a nPose object (without numbered seats), nPose
descides on which seat the new sitter is placed. By default new sitters are
placed on the free seat with the lowest seat number. If you set 
``seatAssignList=d`` a new sitter will be placed on the free seat with the
highest seat number. If you set ``seatAssignList=r`` a seat will be randomly
choosen. You can also add more values to the list, for example
``seatAssignList=1,5,r`` which means: If seat 1 is free then place a new sitter
on seat 1, if not then try seat 5. If seat 5 is also occupied then choose a
ramdom seat.
