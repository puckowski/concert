[Home](https://puckowski.github.io/concert/)

# Text adventure

Demonstration of some Concert Programming Language concepts.

## Code

```cpp
import math;
import string;
import io;

struct "room";
	string description;
	string north;
	string east;
	string south;
	string west;
struct;

new "room" "r1";
new "room" "r2";
new "room" "r3";

r1.description = "Lobby";
r1.north = "r2";
r1.east = "";
r1.south = "";
r1.west = "";

r2.description = "Hallway";
r2.north = "r3";
r2.east = "";
r2.south = "r1";
r2.west = "";

r3.description = "Study";
r3.north = "";
r3.east = "";
r3.south = "r2";
r3.west = "";

string currentRoom = "r1";

function printRooms : string as forRoom;
	println "You are in: ", forRoom.description;
	print "Rooms available: ";
	
	if forRoom.north != "";
		print "north ";
	end;
	if forRoom.east != "";
		print "east ";
	end;
	if forRoom.south != "";
		print "south ";
	end;
	if forRoom.west != "";
		print "west ";
	end;
	
	println "";
return;

function goToRoom : string as currRoom, string as exitRoom;
	string newRoom;
	
	call to_lower_case : exitRoom -> exitRoom;
	
	if exitRoom == "north";
		if currRoom.north != "";
			newRoom = currRoom.north;
		end;
	end;
	
	if exitRoom == "east";
		if currRoom.east != "";
			newRoom = currRoom.east;
		end;
	end;
	
	if exitRoom == "south";
		if currRoom.south != "";
			newRoom = currRoom.south;
		end;
	end;
	
	if exitRoom == "west";
		if currRoom.west != "";
			newRoom = currRoom.west;
		end;
	end;
return newRoom;

string input;

println "Welcome to Concert Simple Text Adventure!";
println "Type \"help\" for help.";

# Game loop
while input != "exit";
	call printRooms : currentRoom;

	println "Go where?";
	print "> ";
	readln input;
		
	if input != "";	
		if input == "help";
			println "Type name of exit to go to new room.";
		else;
			string saveOldRoom = currentRoom;
			call goToRoom : currentRoom, input -> currentRoom;
			
			if currentRoom == "";
				currentRoom = saveOldRoom;
			end;
		end;
	end;
end;

println "Goodbye!";
```