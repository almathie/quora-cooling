#Datacenter Cooling
We have some rooms in our datacenter, and we need to connect them all with a single cooling duct.

##Here are the rules:
* The datacenter is represented by a 2D grid.
* Rooms we own are represented by a 0.
* Rooms we do not own are represented by a 1.
* The duct has to start at the air intake valve, which is represented by a 2.
* The duct has to end at the air conditioner, which is represented by a 3.
* The duct cannot go in multiple directions out of the intake or the AC - they must be the two endpoints of the duct.
* The duct must pass through each room exactly once.
* The duct cannot pass through rooms we do not own.
* The duct can connect between rooms horizontally or vertically but not diagonally.
* Here is an example datacenter:
2  0  0  0

0  0  0  0

0  0  3  1
        
There are two possible ways to run the duct here:

2--0--0--0
         |
0--0--0--0
|
0--0--3  1
or

2  0--0--0
|  |     |
0  0  0--0
|  |  |
0--0  3  1
Write a program to compute the number of possible ways to run the duct. For the above example, the correct answer is 2.

## The solution
My solution implements a recursive depth-first-search algorithm.
In order to give results in a acceptable amount of time, branches should be pruned as soon as possible.
Two pruning mechanism are put into place :
* If a room adjascent to the current room only has one other exit, the program does not visit any other room
* When a room is visited, the program verifies that the adjascent rooms can still connect to the exit. This is done using the A* algorithm

Also, similar branches are merged toegether.
Two branches are similar if the rooms hat have been visited are the same and if the current room is the same.
This is done using a simple key/value store : the key is a string representation of the board and the value is the number of possible path.

##The results
The "advanced" board : 
2 0 0 0 0 0 0
0 0 0 0 0 0 0
0 0 0 0 0 0 0
0 0 0 0 0 0 0
0 0 0 0 0 0 0
0 0 0 0 0 0 0
0 0 0 0 0 0 0
3 0 0 0 0 1 1
gives the following results on my Macbook Pro 2.26 Ghz :
*301716 solutions in 5193880 steps computed in 408.601 seconds (0.07866970357420656ms / step)*

## How to use
* Compile : coffee -c quora.coffee
* Run : node quora.js


