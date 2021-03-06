[Home](https://puckowski.github.io/concert/)

# Text adventure

Demonstration of some Concert Programming Language concepts.

## Code

```cpp
import math;
import string;
import io;

call seed_random;

const int INVENTORY_CAPACITY = 5;

const int COMMAND_SIZE = 10;
const string COMMANDS COMMAND_SIZE;
COMMANDS[0] = "help";
COMMANDS[1] = "take";
COMMANDS[2] = "use";
COMMANDS[3] = "north";
COMMANDS[4] = "east";
COMMANDS[5] = "south";
COMMANDS[6] = "west";
COMMANDS[7] = "exit";
COMMANDS[8] = "attack";
COMMANDS[9] = "coins";

struct "player";
	int health;
	string inventory 5;
	int inventoryIndex;
	int inventoryCapacity;
	int damage;
	int coins;
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
	string monster;
struct;

struct "monster";
	string name;
	int currentHealth;
	int maxHealth;
	int damage;
	int reward;
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
r1.monster = "m1";

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
p1.inventoryCapacity = INVENTORY_CAPACITY;
p1.inventoryIndex = 0;
p1.damage = 7;
p1.coins = 0;

new "monster" "m1";

m1.name = "Goblin";
m1.currentHealth = 6;
m1.maxHealth = 6;
m1.damage = 3;
m1.reward = 10;

string currentRoom = "r1";

function printRooms : string as forRoom;
	println "You are in: ", forRoom.description;
	
	if forRoom.item != "";
		string item = forRoom.item;
		println "There is something on the ground: ", item.name;
	end;
	
	if forRoom.monster != "";
		string monster = forRoom.monster;
		println "There is a ", monster.name, " spawn here.";
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
	int index = 0;
			
	while i < p1.inventoryCapacity;
		string item = p1.inventory[useItem.index];
								
		if item != "";
			if item.name == toUse;	
				println "Used: ", item.name;
				
				p1.inventory[useItem.index] = "";
				p1.health += item.healValue;
				
				println "Health: ", p1.health;
			end;			
		end;
					
		index += 1;
		i += 1;
	end;
return;

function takeItem : string as currentRoom, string as item;
	int i = 0;
	int took = 0;
	
	while i < p1.inventoryCapacity;
		if p1.inventory[takeItem.i] == "";
			p1.inventory[takeItem.i] = item;
			p1.inventoryIndex += 1;
					
			currentRoom.item = "";
			took = 1;
			break;
		end;
		
		i += 1;
	end;
	
	if took == 1;
		println "You took the ", item.name, ".";
	else;
		println "Your inventory is full.";
	end;
return;

function printHelp : using COMMAND_SIZE, using COMMANDS;
	print "Commands: ";
	
	int i = 0;
	
	while i < COMMAND_SIZE;
		print COMMANDS[i], " ";
		i += 1;
	end;
	
	println "";
return;

function attackEnemy : string as currentRoom;
	string monster = currentRoom.monster;
	
	if monster != "";
		println "You attack the ", monster.name, ".";
		
		int damage = monster.damage;
		p1.health -= damage;
		println "You take ", damage, " damage.";
		
		if p1.health <= 0;
			println "You were slain!";
		else;
			int att;
			call get_random -> att;
			att = att % p1.damage;
			
			monster.currentHealth -= att;
			println "The ", monster.name, " took ", att, " damage.";
			
			if monster.currentHealth <= 0;
				println "You have slain the ", monster.name, "!";
				p1.coins += monster.reward;
				println "You received ", monster.reward, " coins.";
				
				monster.currentHealth = monster.maxHealth;
			end;
		end;
	end;
return;

function readConfigurationFile;
	int fileExist;
	call is_file_exist : "concert_adventure.cfg" -> fileExist;

	if fileExist == 1;
		call open_file : "concert_adventure.cfg";
		
		int isOpen;
		call is_open : "concert_adventure.cfg" -> isOpen;
		
		if isOpen == 1;
			string line;
		
			call get_line : "concert_adventure.cfg" -> line;
			int fileHealth;
			call to_int : line -> fileHealth;
			
			# If not dead...
			if fileHealth > 0;
				p1.health = fileHealth;
				
				call get_line : "concert_adventure.cfg" -> line;
				int fileInventoryIndex;
				call to_int : line -> fileInventoryIndex;
				p1.inventoryIndex = fileInventoryIndex;
				
				call get_line : "concert_adventure.cfg" -> line;
				int fileCoins;
				call to_int : line -> fileCoins;
				p1.coins = fileCoins;
				
				int invIndex = 0;
				while invIndex < p1.inventoryCapacity;
					call get_line : "concert_adventure.cfg" -> line;
					p1.inventory[readConfigurationFile.invIndex] = line;
					invIndex += 1;
				end;
			end;
			
			call close_file : "concert_adventure.cfg";
		else;
			println "Failed to read configuration file.";
		end;
	end;
return;

function writeConfigurationFile;
	call remove_file : "concert_adventure.cfg";
	call create_file : "concert_adventure.cfg";
	
	call open_file : "concert_adventure.cfg";
	
	int isOpen;
	call is_open : "concert_adventure.cfg" -> isOpen;
	
	if isOpen == 1;
		string toWrite;
		
		call int_to_string : p1.health -> toWrite;
		call write_string : "concert_adventure.cfg", toWrite;
		call write_string : "concert_adventure.cfg", "\n";
		
		call int_to_string : p1.inventoryIndex -> toWrite;
		call write_string : "concert_adventure.cfg", toWrite;
		call write_string : "concert_adventure.cfg", "\n";
		
		call int_to_string : p1.coins -> toWrite;
		call write_string : "concert_adventure.cfg", toWrite;
		call write_string : "concert_adventure.cfg", "\n";
		
		int invIndex = 0;
		while invIndex < p1.inventoryCapacity;
			call write_string : "concert_adventure.cfg", p1.inventory[writeConfigurationFile.invIndex];
			invIndex += 1;
			
			if invIndex != p1.inventoryCapacity;
				call write_string : "concert_adventure.cfg", "\n";
			end;
		end;
		
		call close_file : "concert_adventure.cfg";
	else;
		println "Failed to save configuration file.";
	end;
return;

call readConfigurationFile;

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
			call printHelp : COMMAND_SIZE, COMMANDS;
			
			continue;
		end;
		
		if input == "health";
			println "Health: ", p1.health;
			
			continue;
		end;
		
		if input == "use";	
			println "Use what?";
			print "> ";
			readln input;
			
			call useItem : input;
			
			continue;
		end;
		
		if input == "take";
			if currentRoom.item != "";
				string item = currentRoom.item;

				call takeItem : currentRoom, item;
			end;
			
			continue;
		end;
		
		if input == "attack";
			call attackEnemy : currentRoom;
			
			if p1.health <= 0;
				break;
			end;
			
			continue;
		end;
		
		if input == "coins";
			println "You have ", p1.coins, " coins.";
			
			continue;
		end;
		
		string newRoom;
		call goToRoom : currentRoom, input -> newRoom;
			
		if newRoom != "";
			currentRoom = newRoom;
		end;
	end;
end;

call writeConfigurationFile;

println "Goodbye!";
```