[Home](https://puckowski.github.io/concert/)

# Text adventure

Demonstration of some Concert Programming Language concepts.

## Code

```cpp
import math;
import string;
import io;

const int COMMAND_SIZE = 8;
string commands COMMAND_SIZE;
commands[0] = "help";
commands[1] = "take";
commands[2] = "use";
commands[3] = "north";
commands[4] = "east";
commands[5] = "south";
commands[6] = "west";
commands[7] = "exit";

struct "player";
	int health;
	string inventory 5;
	int inventoryIndex;
	int inventoryCapacity;
	int index;
struct;

struct "item";
	string name;
	int healValue;
struct;

struct "room";
	string item;
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
r1.item = "i1";
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

new "item" "i1";

i1.name = "Amulet";
i1.healValue = 5;

new "player" "p1";
p1.health = 10;
p1.inventoryCapacity = 5;
p1.inventoryIndex = 0;

string currentRoom = "r1";

function printRooms : string as forRoom;
	println "You are in: ", forRoom.description;
	
	if forRoom.item != "";
		string item = forRoom.item;
		println "There is something on the ground: ", item.name;
	end;
	
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
	string newRoom = "";
	
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

function useItem : string as toUse;
	int i = 0;
	p1.index = 0;
			
	while i < p1.inventoryCapacity;
		string item = p1.inventory[index];
								
		if item != "";
			if item.name == toUse;	
				println "Used: ", item.name;
				
				p1.inventory[index] = "";
				p1.health += item.healValue;
				
				println "Health: ", p1.health;
			end;			
		end;
					
		p1.index += 1;
		i += 1;
	end;
return;

function takeItem : string as currentRoom, string as item;
	if p1.inventoryIndex < p1.inventoryCapacity;
		p1.inventory[inventoryIndex] = item;
		p1.inventoryIndex += 1;
					
		currentRoom.item = "";
	end;
return;

function printHelp : using COMMAND_SIZE, using commands;
	print "Commands: ";
	
	int i = 0;
	
	while i < COMMAND_SIZE;
		print commands[i], " ";
		i += 1;
	end;
	
	println "";
return;

string input;

println "Welcome to Concert Simple Text Adventure!";
println "Type \"help\" for help.";

# Game loop
while input != "exit";
	if p1.health == 0;
		break;
	end;

	call printRooms : currentRoom;

	println "Go where?";
	print "> ";
	readln input;
		
	if input != "";	
		if input == "help";
			println "Type name of exit to go to new room.";
			int cs = 2;
			call printHelp;

			break 7;
		end;
		
		if input == "health";
			println "Health: ", p1.health;
		
			break 6;
		end;
		
		if input == "use";	
			println "Use what?";
			print "> ";
			readln input;
			
			call useItem : input;
			
			break 5;
		end;
		
		if input == "take";
			if currentRoom.item != "";
				string item = currentRoom.item;

				call takeItem : currentRoom, item;
			end;
			
			break 3;
		end;
		
		string newRoom;
		call goToRoom : currentRoom, input -> newRoom;
			
		if newRoom != "";
			currentRoom = newRoom;
		end;
	end;
end;

println "Goodbye!";
```