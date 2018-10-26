[Home](https://puckowski.github.io/concert/) <span>&emsp;</span> [Keywords](https://puckowski.github.io/concert/keywords.html)

# Keyword struct

## Descrption

Used to define a struct template.

## Example

```cpp
# struct with name "coordinate"
struct "coordinate";
	int x;
	int y;
struct;

# new struct is named c1
new "coordinate" "c1";

c1.x = 101;
c1.y = 202;

string structName = "randomTuple";

# struct with name "randomTuple"
struct structName;
	double data;
	string name;
struct;
```