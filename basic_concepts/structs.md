[Home](https://puckowski.github.io/concert/)

# Structs

Concert supports creation of structs, or structures. Structs are templates for containers which store data. Structs may contain any combination of any primitive type, barring mutexes. New structs are created using the new keyword and their members are referenced by using the "." scope operator.

## Struct examples

```cpp
struct "coordinate";
	int x;
	int y;
struct;

new "coordinate" "c1";

c1.x = 101;
c1.y = 202;

string alternateAccess = "c1";

# Modify x and y using a variable name which has a reference to struct instance "c1"
alternateAccess.x = 303;
alternateAccess.y = 404;
```