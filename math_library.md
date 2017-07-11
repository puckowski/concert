[Home](https://puckowski.github.io/concert/) <span>&emsp;</span> [Standard library](https://puckowski.github.io/concert/standard_library.html)

# Math library

Provides standard math functions.

## Import

The following statement may be used to import the math library:

```cpp
import math;
```

## Functions

| Name          | Description                                        |
|:--------------|:---------------------------------------------------|
| seed_random   | Seed the random number generator using system time |
| get_random    | Get a random integer                               |
| int_to_double | Convert an integer to a double                     |
| double_to_int | Convert a double to an integer                     |

## Examples

### seed_random

```cpp
call seed_random;
```

### get_random

```cpp
int rand;
call get_random -> rand;
```

### int_to_double

```cpp
int iToD = 5;
double tempDouble;

call int_to_double : iToD -> tempDouble;
```

### double_to_int

```cpp
int dToI = -1;
double tempDouble;

call double_to_int : tempDouble -> dToI;
```