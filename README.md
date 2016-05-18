# CS344-Adventure
Program 2 - Operating Systems - Reading/Writing to Files in C on UNIX

This assignment asks you to write a simple game akin to old text adventure games like [Adventure](http://en.wikipedia.org/wiki/Colossal_Cave_Adventure)

#### Overview
Your program will first create a series of files that hold descriptions of the rooms and how rooms are connected, and then it will offer to the player an interface for playing the game using those generated rooms. The player will begin in the “starting room” and will win the game automatically upon entering the “ending room”. Finally, the program will exit and display the path taken by the player.

#### Specifications
The first thing your program must do is generate 7 different room files, one room per file, in a directory called <username>.rooms.<process id>. You get to pick the names for those files, which should be hardcoded into your program.

Each room has a Room Name, at least 3 outgoing connections (and at most 6 outgoing connections, where the number of outgoing connections is random) from this room to other rooms, and a room type. The connections from one room to the others should be randomly assigned – i.e. which rooms connect to each other one is random but note that if room A connects to room B, then room B must have a connection back to room A. Because of these specs, there will always be at least one path through. Note that a room cannot connect to itself.

Choose a list of ten different Room Names, hard coded into your program, and have your program randomly assign a room name to each room generated. For a given run of your program, 7 of the 10 room names will be used. Note that a room name cannot be used to in more than one room, The possible room type entries are: START_ROOM, END_ROOM, and MID_ROOM. The assignment of which room gets which type should be random. Naturally, only one room should be assigned as the start room, and only one room should be assigned as the end room.

Upon being executed, after the rooms are generated, the game should present an interface to the player. Note that the room data must be read back into the program from the files, for use by the game.

This interface should list where the player current is, and list the possible connections that can be followed. It should also then have a prompt.
- When the user types in the exact name of a connection to another room, and then hits return, your program should write a new line, and then continue running as before.
- If the user types anything but a valid room name from this location (case matters!), the program should return an error line that says “HUH? I DON’T UNDERSTAND THAT ROOM. TRY AGAIN.”, and repeat the current location and prompt.
- Trying to go to an incorrect location does not increment the path history or the step count. Once the user has reached the End Room, the program should indicate that it has been reached. It should also print out the path the user has taken to get there, the number of steps, and a congratulatory message.
