[Home](https://puckowski.github.io/concert/) <span>&emsp;</span> [Standard library](https://puckowski.github.io/concert/standard_library.html)

# String library

Provides standard string functions.

## Import

The following statement may be used to import the string library:

```cpp
import string;
```

## Functions

| Name             | Description                                            |
|:-----------------|:-------------------------------------------------------|
| substring        | Return a substring                                     |
| find             | Find the index of a substring                          |
| contains         | Check the existence of a substring                     |
| length           | Return the length                                      |
| to_int           | Convert to an integer type                             |
| to_double        | Convert to a double type                               | 
| char_at          | Return the character at an index                       |
| char_to_string   | Convert a character, stored in an integer, to a string |
| int_to_string    | Convert an integer to a string                         |
| double_to_string | Convert a double to a string                           |
| char_to_int      | Convert a character to an integer                      |

## Examples

### substring

```
const string SUBSTRING_TEST_STRING = "This is a test string.";
string testSubstring;
call substring : SUBSTRING_TEST_STRING, 0, 4 -> testSubstring;
```

### find

```
const string FIND_TEST_STRING = "This is a test string.";
int findResult = -1;
call find : FIND_TEST_STRING, "a" -> findResult;
```

### contains

```
const string CONTAINS_TEST_STRING = "This is a test string.";
int containsResult;
call contains : CONTAINS_TEST_STRING, "This" -> containsResult;
```

### length

```
const string LENGTH_TEST_STRING = "This is a test string.";
int testStringLength = -1;
call length : LENGTH_TEST_STRING -> testStringLength;
```

### to_int

```
string firstChar = "?";
int charInt = -1;
call char_to_int : firstChar -> charInt;
```

### to_double

```
string sToD = "2.718";
tempDouble = -1.0;
call to_double : sToD -> tempDouble;
```

### char_at

```
const string CHAR_AT_TEST_STRING = "This is a test string.";
string firstChar = "?";
call char_at : CHAR_AT_TEST_STRING, 0 -> firstChar;
```

### char_to_string

```
int byte;
string char;
call char_to_string : byte -> char;
```

### int_to_string

```
int iToS = 234;
string tempString = "?";
call int_to_string : iToS -> tempString;
```

### double_to_string

```
double dToS = 3.14;
tempString = "?";
call double_to_string : dToS -> tempString;
```

### char_to_int

```
string firstChar = "?";
int charInt = -1;
call char_to_int : firstChar -> charInt;
```
