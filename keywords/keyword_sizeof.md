[Home](https://puckowski.github.io/concert/) <span>&emsp;</span> [Keywords](https://puckowski.github.io/concert/keywords.html)

# Keyword sizeof

## Description

Returns the size of a variable.

## Notes

Size represents the number of elements contained by that variable, not the number of bytes used by that variable.

## Example

```cpp
int numArray 100 = 0;
int sizeOfNumArray = 0;

# sizeOfNumArray is set to 100.
# Note that numArray's size is 100 while it uses 400 bytes (of memory).
sizeof numArray sizeOfNumArray;
```
