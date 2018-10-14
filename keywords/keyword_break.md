[Home](https://puckowski.github.io/concert/) <span>&emsp;</span> [Keywords](https://puckowski.github.io/concert/keywords.html)

# Keyword break

## Description

Stops execution of the enclosing code block.

## Example

```cpp
# Infinite loop
while 1 == 1;
    println "Infinite loop...";
    # Stop infinite while loop
    break; 
end;

# Infinite loop. Exit two end cases to break while loop.
int x = 5;
int y = 5;

while 1 == 1;
	if x == y;
		break 2;
	end;
end;
```
