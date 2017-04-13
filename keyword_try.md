# Keyword try

## Description

Declares a try-block statement to handle potentially unsafe code.

## Example

```cpp
int dividend = 10;
int divisor = 0;

try;
  int quotient = dividend / divisor;
catch;
  println "Exception occurred when calculating quotient.";
end;
```