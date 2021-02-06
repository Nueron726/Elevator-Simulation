# Elevator-Simulation
While the generic implementations of a stack and queue are great, they don't necessarily work for all cases.  Custom versions of these data types are sometimes still needed.  Consider the following situation:

You have a long, narrow elevator with only one door.  The design of the elevator makes it impossible for people in the elevator to pass each other, but the elevator is very deep and can hold 20 people.  As such, in order for someone in the back (side furthest from the door) of the elevator to leave the elevator, everyone else in the elevator must first exist.  This is very inconvenient for the everyone involved.  Corporate has proposed that instead of everyone getting off and on the elevator every time someone in the back needs to get off the elevator, only the person at the front (nearest the door side) is allowed to get off the elevator.  (NOTE: If the first n people all want to get off at the current floor, they can.  But once the current "top" of the stack is a person who does NOT want to exit the elevator, no one else can exit the elevator at this time.)  Additionally, Corporate as dictated that on a given floor stop, all allowable "pop" operations must occur before any "push" operations.

Things we will need:

-An ElevatorRider Object which MUST have AT LEAST:
An identifier of some kind (name, employee number, etc....  Pick what you want!)
A frustration level (start at zero)
A target floor they want to get off the elevator at
Get and Set methods for all of the above attributes
A toString() method

-A Custom Built Stack which (at MINIMUM):
Only is used for storing ElevatorRider Objects
Has a push()
Has a pop()
Has a peek()
Has a method raise the frustration level of all passengers still on the Stack [This method is why we need the custom Stack]

-A Driver to setup and run the simulation.
Generate Riders and have "Day Shift" Riders set to arrive in a random order (i.e., not all floor 5 riders can arrive first)
Setup the "building"...I recommend using an array of Queues
Running the Morning Mode and the Evening Mode

-The building will initially have:

5 floors [1 through 5, 5 being the highest and 1 being "ground level"].  I would suggest each floor have its own queue (you could use a built-in Java queue for this as I am NOT requiring that people waiting to get onto the Elevator accrue frustration).
350 Day Shift people divided up as follows:
110 people with "home" on the 5th floor
75 people with "home" on the 4th floor
65 people with "home" on the 3rd floor
100 people with "home" on the 2nd floor
16 Night Shift people divided up as follows:
4 people with "home" on 5th floor
4 people with "home" on 4th floor
4 people with "home" on 3rd floor
4 people with "home" on 2nd floor

-Your Driver should have 2 distinct modes:
Morning Mode:
All "Day Shift" ElevatorRiders will progress from floor 1 to the their "home" floors
All "Night Shift" ElevatorRiders start on their "home" floor and try to get back down to floor 1 to leave for the day. 
All "Night Shift" people should be waiting at the queue for their floor to ride the elevator down at the start of Morning
Every time the Elevator moves between floors, 5 "Day Shift" ElevatorRiders should be added to queue of riders for the 1st floor (unless all 350 "Day Shift" people have already been added to the queue)
When all riders reach their target floor ("home" for day shifters, 1st floor for night shifters), print the average (mean, median, or mode...Just make sure you tell the user which they are receiving) frustration for:
All riders
"Day Shift" riders
"Night Shift" riders

Evening Mode:
All "Day Shift" ElevatorRiders start on their "home" floor and progress to the 1st floor
Every the Elevator moves between floors, 5 "Day Shift" ElevatorRider should be added to their "home" floor queues (unless all 350 people have already been processed)
All "Night Shift" ElevatorRiders will progress from floor 1 to their "home" floor
All "Night Shift" ElevatorRiders should be waiting at the floor 1 queue at the start of this mode
When all riders reach their target floor ("home" for night shifters, 1st floor for day shifters), print the average (same average type you used for Morning Mode) frustration for:
All riders
"Day Shift" riders
"Night Shift" riders
